---
title: LLM 파인튜닝 방법 # 글 제목
date: 2026-06-19 18:00:00 +0900           # 작성 시간
categories: [개발, LLM]                # [상위주제, 하위주제] 순서대로 입력
tags: [파이썬, LLM 튜닝]                  # 태그 지정
---

1. **라이브러리 임포트** <br>   
   import os  <br>
   import torch <br>
   from contextlib import nullcontext <br>
   from datasets import load_dataset <br>
   from peft import get_peft_model, LoraConfig, prepare_model_for_kbit_training <br>
   from transformers import AutoModelForCausalLM, AutoTokenizer, BitsAnyBytesConfig <br>
   from trl import SFTConfig, SFTTrainer <br><br>
2. **양자화된 베이스 모델 로드하기** <br>

   
