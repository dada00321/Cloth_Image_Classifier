# cloth_image_classifier
可用於辨識服飾顏色、種類的服飾圖片分類器

經粗淺的服飾業資訊了解

依照冷、暖、中間色系，將模型「顏色」標籤分為 12 類：

　　紅、橙、黃、粉紅、青、藍、紫、綠、灰、黑、白、咖啡

經目標開發服飾商的資訊調查（和自製的服飾分類歸納工具整理）

統一將服飾分類訂為 12 類：

　　上衣類 襯衫類 內衣類 外套類 下身類 配件類 洋裝類 運動類 鞋類 童裝類 嬰幼兒類 孕婦類

原預計對 144 類 顏色x服飾分類 做個別資料集

目前已完成 39 類 個別資料集

分類器模型： VGGNet

訓練資料集： 共 16,039 張服飾圖片

訓練回合數： 75 epochs

模型準確率： 訓練集 => 0.9813

            測試集 => 0.9577

P.S. 因人力有限，目前開發方向以後續的服飾網站後端和延伸功能為主，

有時間再一點一滴補齊剩下的資料集。

P.S. 「已完成」分類資料集(可用來預測該分類，目前共 39 類)：

紅色_外套類 紅色_下身類 紅色_配件類 紅色_洋裝類 紅色_鞋類 紅色_孕婦類 橙色_上衣類
橙色_襯衫類 黃色_童裝類 黃色_嬰幼兒類 黃色_孕婦類 粉紅色_上衣類 青色_襯衫類 青色_內衣類 
灰色_洋裝類 灰色_童裝類 灰色_孕婦類 黑色_上衣類 黑色_襯衫類 黑色_內衣 類 黑色_外套類 
黑色_下身類 黑色_配件類 黑色_洋裝類 黑色_鞋類 黑色_童裝類 黑色_孕婦類 白色_上衣類 
白色_內衣類 白色_外套類 白色_配件類 白色_洋裝類 白色_鞋類 白色_童裝類 白色_孕婦類 
咖啡色_內衣類 咖啡色_配件類 咖啡色_洋裝類 咖啡色_孕婦類

Q： 為何不使用 2 個分類器(顏色、服飾分類) 串聯，減少製備訓練資料的時間成本？

A： 這樣的做法雖然直觀，預測效果也理當不錯，但辨識新資料、甚至辨識大批資料時
    模型的延遲就可能大大降低使用者體驗了。
    
    故採用此方法，將多個預測標籤放入同一模型。
