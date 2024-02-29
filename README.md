# yolox-body-head-hand-face

## Install

```
wget https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge-pypy3-Linux-x86_64.sh
bash Miniforge-pypy3-Linux-x86_64.sh
```

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


## Comparison

### YOLO_N
YOLOX_N - 640x640
```
python demo_yolox_onnx_tfite.py -m models/yolox_n/yolox_n_body_head_hand_face_dist_0221_0.3941_post_1x3x640x640.onnx -i debug_images -ep cuda -dvw -o yolox_n_640x640 -dwk
```

YOLOX_N - 320x320
```
python demo_yolox_onnx_tfite.py -m models/yolox_n/yolox_n_body_head_hand_face_dist_0221_0.3941_post_1x3x640x640.onnx -i debug_images -ep cuda -dvw -o yolox_n_640x640 -dwk
```

### YOLO_S
YOLOX_S - 640x640
```
python demo_yolox_onnx_tfite.py -m models/yolox_s/yolox_s_body_head_hand_face_dist_0189_0.4952_post_1x3x640x640.onnx -i debug_images -ep cuda -dvw -o yolox_s_640x640 -dwk
```
YOLOX_S - 320x320
```
python demo_yolox_onnx_tfite.py -m models/yolox_s/yolox_s_body_head_hand_face_dist_0189_0.4952_post_1x3x320x320.onnx -i /workspace/yolo_v8_training/oiv7_full/train -ep cuda -dvw -dwk
```


## Image Labeler
Install

```
git clone https://github.com/dnth/streamlit-img-label/
cd streamlit-img-label
git checkout data-flywheel
pip install -e .
```

```
streamlit run steamlit_labeler.py --server.fileWatcherType none 
```