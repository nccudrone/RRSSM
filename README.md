# RRSSM：河川/道路影像切割模型 (River/Road Semantic Segmentation Model)

## Overview
此模型為台灣河流與郊區、山區道路俯視角空拍語意切割模型。  
由政大無人機團隊 VIP 實驗室使用 [SeMask-Segmentation](https://github.com/Picsart-AI-Research/SeMask-Segmentation "link") 進行訓練。  
訓練、驗證與測試資料集來自於：[郊區、山區道路俯視角空拍語意切割資料集](https://github.com/nccudrone/SMRAVSSD "link")、[台灣河流(二仁溪、曾文溪與景美溪)俯視角空拍語意切割資料集](https://github.com/nccudrone/RIVERAVSSD "link")。  
訓練GPU：RTX A6000  
模型訓練之記憶體使用量：11000 MB  
模型之使用空間：35 MB  
模型支援之框架與版本：於python3.6與python3.7進行過測試，相關版本見說明。  
模型訓練結果：  
* 郊區、山區道路俯視角空拍語意切割資料集/IoU score=98.68%
* 台灣河流俯視角空拍語意切割資料集/IoU score=98.11%  

用途為對影像進行語意切割，找出河流或是郊、山區道路輪廓，見說明可調整。  
Pretrained Model放置在xxx_model，可根據使用需求調整，xxx可帶入：
* river
* road
* riverandroad

可以執行下列指令(其餘指令見說明)獲得結果，將需要預測的圖片放入在test_image_folder/裡，結果會儲存在demo/output/裡  
```python
python demo/predict.py --config road_model/config.py --checkpoint road_model/latest.pth  
```  
下面為模型預測展示：  
<img src="https://github.com/nccudrone/RRSSM/blob/main/image/river1.png" width="428" height="240"/>  
<img src="https://github.com/nccudrone/RRSSM/blob/main/image/road1.png" width="428" height="240"/><br/>  

## 說明
* 此repo僅包含pretrained model做為免費開放使用
* 此模型用於學術研究
* 訓練、驗證與測試資料集 [郊區、山區道路俯視角空拍語意切割資料集](https://github.com/nccudrone/SMRAVSSD "link")、[台灣河流(二仁溪、曾文溪與景美溪)俯視角空拍語意切割資料集](https://github.com/nccudrone/RIVERAVSSD "link") 僅包含部分免費開放使用資料集。
* 於下載環境設定與模型檔案後，可照裡面的"安裝以及測試指令"來進行使用。  
* 環境設定本身包含virtualenv設定檔，可以直接soure ./venv/bin/activate進行使用。
* 在使用模型時記得根據使用的模型與想要輸出的顏色，來更改mmseg中datasets/drive.py 與 mmseg中core/evaluation/class_names.py
* 如果不想使用virtualenv，也可以根據"安裝以及測試指令"內的pip list清單，來安裝所需套件。

## 環境設定與模型檔案下載
[link](http://140.119.164.183:5000/sharing/IRopIPy78 "link")  
## Licence
請參考 [LICENSE](https://github.com/nccudrone/RRSSM/blob/main/LICENSE "link")
