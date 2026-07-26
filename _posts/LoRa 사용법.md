---
title: 새롭게 검토해야 할 기술 및 소프트웨어 # 글 제목
date: 2026-07-25 18:00:00 +0900           # 작성 시간
categories: [개발, LLM]                # [상위주제, 하위주제] 순서대로 입력
tags: [파이썬, 시뮬레이션]                  # 태그 지정
---
LoRa 파일튜닝 방법 ""COSMOS"" 세부기술 검토

r(랭크) : r이 작을수록 메모리/학습시간이 절약, 단 표현력 제한

lora_alpha : 스케일 조정
    # 실제 적용되는 스케일 = lora_alpha / r
    # config = LoraConfig(r=8, lora_alpha=32) # 스케일 =4, 일반적 권장
    # 일반적으로 r의 2~4배 값을 사용하며, r=8일때, lora_alpha=16 또는 32 가 적절

targent_modules : LoRa를 적용할 모듈 지정
    # 일반적으로 attention의 q_proj, v_proj에 적용
    # config = LoraConfig(r=8, target_modules=["q_proj", "v_proj"])

    # 권장 구성(균형 잡힌 성능, 약 8M 파라미터)
    # config = LoraConfig(r=8, target_modules=["q_proj","k_proj", "v_proj","o_proj"])

    # 전체 구성(최고 성능, 약 4M 파라미터)
    # config = LoraConfig(
    #          r=8, 
    #          target_modules=[
    #            "q_proj","k_proj", "v_proj","o_proj", # 어텐션
    #            "gate_proj", "down_proj", "up_proj" # 피드포워드



from re import A
from transformers import AutoModelForCausalLM
from peft import LoraConfig, get_peft_model

# 1. 기본 모델 로드
model = AutoModelForCausalLM.from_pretrained("beomi/Llama-3-Open-Ko-8B")

#2. LoRa 설정
config = LoraConfig(
    r=8,
    lora_alpha=32,
    target_modules=["q_proj", "v_proj"],
    lora_dropout=0.05)

#3. LoRa 적용
model = get_peft_model(model, config)

# 학습할 수 있는 파라미터 확인
model.print_trainable_parameters()
# 출력: trainable params: 1,048,576 || all params: 8,388,608 || trainable%: 12.50%
