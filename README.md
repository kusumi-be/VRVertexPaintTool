# 前置き
ポートフォリオとして利用しているリポジトリです。 そのため、一般的な利用はあまり想定しておりません。

# 概要
Unity + Meta XR SDK環境において、ハンドトラッキングでオブジェクトを塗るためのスクリプトです。

# 実行例
人指し指で色を塗る設定で動かした場合
<video controls src="2024-09-07 03-51-40.mp4" title="Title"></video>

# 使い方
## PaintToolの使い方
PaintTool.prefabをSceneに置いてから、それぞれの子prefabを設定すれば使えます。

## BrushSetting
Brushの色とサイズを決めれます  
play modeで"Apply Settings"を押さないと反映されません。  

## PaintToolManager
- Meta XR SDKのBuilding Blocksでcamera rigを追加
- PaintToolManagerに、camera rig内のLeftRay、LightRayをアタッチ  
こうすることで、Rayで色塗りできるようになります。  

また、IsColorFixModeをfalseにすると、BrushSettingで指定した色で色塗りできるようになります。  
![alt text](RayInteractor.png)  

## SetColor2White
色をなくしたいオブジェクトを登録すると、Play Mode時に指定したオブジェクトの色がなくなる。  
![alt text](SetColor2White.png)

## GestureManager
PointをONにすると、指さすことで色を塗れます。  
PinchInをONにすると、PinchInで色を塗れます。  
どちらもOFFにすると、常に色を塗れます。  
使う前に、HandとFingerFeatureStateProviderを設定してください。  
![alt text](GestureManager.png)

## Tag
色を塗りたいオブジェクトのTagは、Untagged, Yellow, Brown, Greenのどれかにしてください  
Yellow, Brown, Green Tagのオブジェクトは、Cheese, Baguette, Wineに触ったときだけ色塗りできます。