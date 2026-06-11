---
title: 아이작심(Isaac-sim) 사용법 요약 정리 # 글 제목
date: 2024-06-03 18:00:00 +0900           # 작성 시간
categories: [개발, 아이작심]                # [상위주제, 하위주제] 순서대로 입력
tags: [파이썬, 시뮬레이션]                  # 태그 지정
---

### Minkowski
sfa@HW20241029-01:~/miniconda3/envs/minkowski$ pwd  

/home/sfa/miniconda3/envs/minkowski  

sfa@HW20241029-01:~/miniconda3/envs/minkowski$ conda activate minkowski  

(minkowski) sfa@HW20241029-01:~/miniconda3/envs/minkowski$   



### AnyDexGrasp

(minkowski) sfa@HW20241029-01:~/AnyDexGrasp$ pwd  

**/home/sfa/AnyDexGrasp**  

(minkowski) sfa@HW20241029-01:~/AnyDexGrasp$ ls
README.md                                  generate_mesh_and_pointcloud  robot_dh3.py
__pycache__                                get_camK.py                   robot_inspire.py
collect_allegro_grasp_data.py              knn                           train.py
collect_dh3_grasp_data.py                  logs                          train_multifinger.py
collect_inspire_grasp_data.py              models                        update_data.py
command_collect_multifinger_grasp_data.sh  pointcloud_to_image.py        ur_toolbox
command_generate_mesh_file.sh              pointnet2                     utils
command_robot_multifinger_grasp.sh         process_pregen_label.py       wsl_grasp_server_data_collector_ADG_v2.py
command_train_multifinger_decision.sh      realsense.py                  wsl_inference_server_ADG_v2.py
command_train_representation.sh            requirements.txt
dataset                                    robot_allegro.py  


**(minkowski) sfa@HW20241029-01:~/AnyDexGrasp$ python wsl_inference_server_ADG_v2.py**  

🔥 Robust Multi-Finger Inference Server Starting...
Loading Base GraspNet...
✅ Base GraspNet Loaded.

Loading Decision Models...
   👉 Found best model: 0.9_0.6551_0.3201_0.4082_120.pth
✅ Loaded Type 1 (Power_Grasp)
   👉 Found best model: 0.9_0.8421_0.166_0.269_99.pth
✅ Loaded Type 2 (Pinch_Grasp)
   👉 Found best model: 0.9_0.7911_0.2432_0.3585_271.pth
✅ Loaded Type 3 (Tripod_Grasp)
   👉 Found best model: 0.9_0.8732_0.1565_0.256_260.pth
✅ Loaded Type 4 (F_Tripod_Grasp)

🚀 Ready for requests...  


<img width="1130" height="487" alt="image" src="https://github.com/user-attachments/assets/c8cae10a-9c5b-49a4-84e7-14e796008956" />



* **두꺼운 글씨**나 *기울임*도 표현할 수 있습니다.
