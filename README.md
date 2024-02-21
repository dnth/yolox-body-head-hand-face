# yolox-body-head-hand-face

## Install

```
apt install python3
apt install python3-pip
```

```
pip install opencv-python-headless pandas onnxruntime tqdm pyarrow matplotlib
```

## CPU Inference

```
python3 demo_yolox_onnx_tfite.py -m yolox_n_body_head_hand_face_dist_0221_0.3941_post_1x3x640x640.onnx -i -i /workspace/yolo_v8_training/oiv7_full/validation/ -dwk
```

## GPU Inference

```
conda install cudatoolkit cudnn
```

```
pip install onnxruntime-gpu
```

```
python3 demo_yolox_onnx_tfite.py -m yolox_n_body_head_hand_face_dist_0221_0.3941_post_1x3x640x640.onnx -i /workspace/yolo_v8_training/oiv7_full/validation/ -ep cuda -dwk
```

## Live Inference

```
python demo_yolox_onnx_tfite.py -m models/yolox_s/yolox_s_body_head_hand_face_dist_0189_0.4952_post_1x3x128x160.onnx -v 0 -ep cuda -dvw
```