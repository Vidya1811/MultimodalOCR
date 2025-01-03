# OCRBench: On the Hidden Mystery of OCR in Large Multimodal Models 
<img src="./images/all_data.png" width="96%" height="96%">

> Large models have recently played a dominant role in natural language processing and multimodal vision-language learning. However, their effectiveness in text-related visual tasks remains relatively unexplored. In this paper, we  conducted a comprehensive evaluation of Large Multimodal Models, such as GPT4V and Gemini, in various text-related visual tasks including Text Recognition, Scene Text-Centric Visual Question Answering (VQA), Document-Oriented VQA, Key Information Extraction (KIE), and Handwritten Mathematical Expression Recognition (HMER). To facilitate the assessment of Optical Character Recognition (OCR) capabilities in Large Multimodal Models, we propose OCRBench, a comprehensive evaluation benchmark. Our study encompasses 29 datasets, making it the most comprehensive OCR evaluation benchmark available. Furthermore, our study reveals both the strengths and weaknesses of these models, particularly in handling multilingual text, handwritten text, non-semantic text, and mathematical expression recognition. Most importantly, the baseline results showcased in this study could provide a foundational framework for the conception and assessment of innovative strategies targeted at enhancing zero-shot multimodal techniques.

**[Project Page [This Page]](https://github.com/Yuliang-Liu/MultimodalOCR)** | **[Paper](https://arxiv.org/abs/2305.07895)** |**[OCRBench Leaderboard](https://huggingface.co/spaces/echo840/ocrbench-leaderboard)**|**[Opencompass Leaderboard](https://rank.opencompass.org.cn/leaderboard-multimodal)**|


# Data
| Data | Link | Description |
| --- | --- | --- |
| Full Test Json | [Full Test](./OCRBench/FullTest.json) | This file contains the test data used in Table 1 and Table 2 from [Paper](https://arxiv.org/abs/2305.07895). |
| OCRBench Json | [OCRBench](./OCRBench/OCRBench.json) | This file contains the test data in OCRBench used in Table3 from [Paper](https://arxiv.org/abs/2305.07895). |
| All Test Images |[All Images](https://drive.google.com/file/d/1U5AtLoJ7FrJe9yfcbssfeLmlKb7dTosc/view?usp=drive_link) | This file contains all the testing images used in [Paper](https://arxiv.org/abs/2305.07895), including OCRBench Images.|
| OCRBench Images | [OCRBench Images](https://drive.google.com/file/d/1a3VRJx3V3SdOmPr7499Ky0Ug8AwqGUHO/view?usp=drive_link) | This file only contains the images used in OCRBench. |
| Test Results | [Test Results](https://drive.google.com/drive/folders/15XlHCuNTavI1Ihqm4G7u3J34BHpkaqyE?usp=drive_link) | This file file contains the result files for the test models. |


# OCRBench

OCRBench is a comprehensive evaluation benchmark designed to assess the OCR capabilities of Large Multimodal Models. It comprises five components: Text Recognition, SceneText-Centric VQA, Document-Oriented VQA, Key Information Extraction, and Handwritten Mathematical Expression Recognition. The benchmark includes 1000 question-answer pairs, and all the answers undergo manual verification and correction to ensure a more precise evaluation. 

You can find the results of Large Multimodal Models in **[OCRBench Leaderboard](https://huggingface.co/spaces/echo840/ocrbench-leaderboard)**, if you would like to include your model in the OCRBench leaderboard, please follow the evaluation instructions provided below and feel free to contact us via email at zhangli123@hust.edu.cn. We will update the leaderboard in time.

<img src="./images/GPT4V_Gemini.png" width="96%" height="96%">

# Evaluation
The test code for evaluating models in the paper can be found in [scripts](./scripts). Before conducting the evaluation, you need to configure the model weights and environment based on the official code link provided in the scripts. If you want to evaluate other models, please edit the "TODO" things in [example](./example.py).

You can also use [VLMEvalKit](https://github.com/open-compass/VLMEvalKit) and [lmms-eval](https://github.com/EvolvingLMMs-Lab/lmms-eval) for evaluation.

Example evaluation scripts:
```python

python ./scripts/monkey.py --image_folder ./OCRBench_Images --OCRBench_file ./OCRBench/OCRBench.json --save_name Monkey_OCRBench --num_workers GPU_Nums # Test on OCRBench
python ./scripts/monkey.py --image_folder ./OCRBench_Images --OCRBench_file ./OCRBench/FullTest.json --save_name Monkey_FullTest --num_workers GPU_Nums # Full Test

```

# Citation
If you wish to refer to the baseline results published here, please use the following BibTeX entries:
```BibTeX
@article{Liu_2024,
    title={OCRBench: on the hidden mystery of OCR in large multimodal models},
    volume={67},
    ISSN={1869-1919},
    url={http://dx.doi.org/10.1007/s11432-024-4235-6},
    DOI={10.1007/s11432-024-4235-6},
    number={12},
    journal={Science China Information Sciences},
    publisher={Springer Science and Business Media LLC},
    author={Liu, Yuliang and Li, Zhang and Huang, Mingxin and Yang, Biao and Yu, Wenwen and Li, Chunyuan and Yin, Xu-Cheng and Liu, Cheng-Lin and Jin, Lianwen and Bai, Xiang},
    year={2024},
    month=dec }
```



