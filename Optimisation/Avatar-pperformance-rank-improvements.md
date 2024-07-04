# アバターのパフォーマンスランクを改善する

アバターのパフォーマンスランクを改善し軽いアバターにするためのワークフロー

## 目次

// ここは自動で生成されます。手動での編集は避けてください。
<!-- TOC -->

- [アバターのパフォーマンスランクを改善する](#%E3%82%A2%E3%83%90%E3%82%BF%E3%83%BC%E3%81%AE%E3%83%91%E3%83%95%E3%82%A9%E3%83%BC%E3%83%9E%E3%83%B3%E3%82%B9%E3%83%A9%E3%83%B3%E3%82%AF%E3%82%92%E6%94%B9%E5%96%84%E3%81%99%E3%82%8B)
    - [目次](#%E7%9B%AE%E6%AC%A1)
    - [Avatar Optimizer](#avatar-optimizer)
    - [不要なオブジェクトの削除](#%E4%B8%8D%E8%A6%81%E3%81%AA%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E3%81%AE%E5%89%8A%E9%99%A4)
    - [テクスチャの最適化](#%E3%83%86%E3%82%AF%E3%82%B9%E3%83%81%E3%83%A3%E3%81%AE%E6%9C%80%E9%81%A9%E5%8C%96)
        - [lilAvatarUtilsのインストール](#lilavatarutils%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB)
        - [lilAvatarUtilsを開く](#lilavatarutils%E3%82%92%E9%96%8B%E3%81%8F)
        - [テクスチャの圧縮](#%E3%83%86%E3%82%AF%E3%82%B9%E3%83%81%E3%83%A3%E3%81%AE%E5%9C%A7%E7%B8%AE)
    - [ポリゴン数の削減](#%E3%83%9D%E3%83%AA%E3%82%B4%E3%83%B3%E6%95%B0%E3%81%AE%E5%89%8A%E6%B8%9B)
        - [ブレンドシェイプでメッシュを消す](#%E3%83%96%E3%83%AC%E3%83%B3%E3%83%89%E3%82%B7%E3%82%A7%E3%82%A4%E3%83%97%E3%81%A7%E3%83%A1%E3%83%83%E3%82%B7%E3%83%A5%E3%82%92%E6%B6%88%E3%81%99)
        - [AAOの Remove Mesh in Boxでさらにポリゴン数を削減する](#aao%E3%81%AE-remove-mesh-in-box%E3%81%A7%E3%81%95%E3%82%89%E3%81%AB%E3%83%9D%E3%83%AA%E3%82%B4%E3%83%B3%E6%95%B0%E3%82%92%E5%89%8A%E6%B8%9B%E3%81%99%E3%82%8B)
        - [Mantis LOD Editorで全体的にポリゴン数を削減する](#mantis-lod-editor%E3%81%A7%E5%85%A8%E4%BD%93%E7%9A%84%E3%81%AB%E3%83%9D%E3%83%AA%E3%82%B4%E3%83%B3%E6%95%B0%E3%82%92%E5%89%8A%E6%B8%9B%E3%81%99%E3%82%8B)
        - [Mantis LOD Editorのインストール](#mantis-lod-editor%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB)
        - [Mantis LOD EditorのNDMF化ツールの導入](#mantis-lod-editor%E3%81%AEndmf%E5%8C%96%E3%83%84%E3%83%BC%E3%83%AB%E3%81%AE%E5%B0%8E%E5%85%A5)
        - [コンポーネントの追加](#%E3%82%B3%E3%83%B3%E3%83%9D%E3%83%BC%E3%83%8D%E3%83%B3%E3%83%88%E3%81%AE%E8%BF%BD%E5%8A%A0)
        - [パラメータの調整](#%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E8%AA%BF%E6%95%B4)
    - [その他](#%E3%81%9D%E3%81%AE%E4%BB%96)

<!-- /TOC -->

## Avatar Optimizer

[Avatar Optimizer](https://vpm.anatawa12.com/avatar-optimizer/ja/docs/reference/trace-and-optimize/)はアバターを非破壊で最適化することができるツール。アバターのゲームオブジェクトのルートに`AAO Trace And Optimize`を追加するだけで最適化ができる。  
![Avatar Optimizer Component](https://img.porop.top/aao-component.png)

## 不要なオブジェクトの削除

アバターのデフォルトの服など使わないものは削除するかEditorOnlyにしておく。Avatar Optimizerを導入している場合はActiveチェックボックスが外されていて使用されていないオブジェクトはビルド時に自動で削除される。
![不要なオブジェクトの削除](https://img.porop.top/gameobject-editor-only.png)

## テクスチャの最適化

テクスチャはVRAMに展開されるため画像サイズが大きいとVRAMを圧迫する。lilAvatarUtilsを使うことで外部のソフトウェアを使わずにテクスチャの圧縮ができる。

### lilAvatarUtilsのインストール

VCCなどパッケージマネージャからlilAvatarUtilsをプロジェクトに追加する。
![lilAvatarUtilsのインストール](https://img.porop.top/add-lilAvatarUtils-package.png)

### lilAvatarUtilsを開く

Unityのメニューから`Window` > `_lil` > `AvatarUtils`を選択する。
![lilAvatarUtilsのメニューを開く](https://img.porop.top/open-AvatarUtils-window.png)

### テクスチャの圧縮

AvatarUtilsウィンドウ上部にアバターの`GameObject`を設定する。
![AvatarUtilsウィンドウのGameObject設定](https://img.porop.top/AvatarUtils-window.png)

`Textures`タブの圧縮したいテクスチャのMax Resolutionを下げたら`Apply`をクリックする。
 ![テクスチャの圧縮](https://img.porop.top/compress-texture-with-AvatarUtils.png)

服や体は2kまで、アクセサリなど小さいものはさらに下げるのがおすすめ。

## ポリゴン数の削減

不要なメッシュを削除してポリゴン数を削減する

### ブレンドシェイプでメッシュを消す

服などで素体のメッシュが隠れる場合はAAOの`Remove Mesh By BlendShape`を素体のオブジェクトにアタッチすることでメッシュを削除できる。画像では完全に隠れる腕の一部をブレンドシェイプで消している。
![不要なメッシュを削除](https://img.porop.top/reduce-mesh-by-blendshape.png)

### AAOの Remove Mesh in Boxでさらにポリゴン数を削減する

ブレンドシェイプが存在しない場合や対応していない場所のメッシュを削除するにはAAOのRemove Mesh in Boxを使う。削除したいメッシュのあるオブジェクトに`Remove Mesh in Box`をアタッチしEdit This BoxをクリックしてBoxの位置とサイズを調整する。
![Remove Mesh in Boxのパラメータ](https://img.porop.top/aao-remove-mesh-box-component.png)

画像のようにこのBox内にあるメッシュがビルド時に削除されるので必要な部分も削除しないように注意。
![Remove Mesh in Boxの使い方](https://img.porop.top/aao-mesh-delete-box-test.png)

### Mantis LOD Editorで全体的にポリゴン数を削減する

[Mantis LOD Editor](https://assetstore.unity.com/packages/tools/modeling/mantis-lod-editor-professional-edition-37086)を使ってアバターの見た目を極力変えずにポリゴン数を削減することができる。さらに[Mantis LOD EditorのNDMF化ツール](https://booth.pm/ja/items/5409262)を使うことで非破壊での使用が可能。

### Mantis LOD Editorのインストール

Unity Asset StoreからMantis LOD Editorをインストールする。

### Mantis LOD EditorのNDMF化ツールの導入

BoothからMantis LOD EditorのNDMF化ツールをダウンロードし、インストールする。

### コンポーネントの追加

ポリゴン数を削減したいオブジェクトに`NDMF Mantis LOD Editor`を追加する。

### パラメータの調整

Previewボタンをクリックしアバターを見ながら`NDMF Mantis LOD Editor`のパラメータを調整してポリゴン数を削減する。
![Mantis LOD Editorのコンポーネント](https://img.porop.top/mantis-lod-editor-component.png)  
適用前(3万△)
![Mantis LOD Editor適用前](https://img.porop.top/mantis-lod-before.png)

適用後(2万△)
![Mantis LOD Editor適用後](https://img.porop.top/mantis-lod-after.png)
このツールはオブジェクトの形によっては大きく見た目が変わることがあるので注意。

## その他

ほかにもマテリアルやメッシュの結合, PBの削減, Skinned Meshの統合, ライトやパーティクルの削減などできることは多いので今後追記予定。
