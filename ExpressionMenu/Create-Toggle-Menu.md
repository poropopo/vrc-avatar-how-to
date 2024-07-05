# 服やアイテムの出し入れを行うためのトグルメニューを作成する

Avatar Menu Creater for Modular Avatarを使って、服やアイテムの出し入れを行うためのトグルメニューを作成する方法

## 目次
<!-- TOC -->

- [服やアイテムの出し入れを行うためのトグルメニューを作成する](#%E6%9C%8D%E3%82%84%E3%82%A2%E3%82%A4%E3%83%86%E3%83%A0%E3%81%AE%E5%87%BA%E3%81%97%E5%85%A5%E3%82%8C%E3%82%92%E8%A1%8C%E3%81%86%E3%81%9F%E3%82%81%E3%81%AE%E3%83%88%E3%82%B0%E3%83%AB%E3%83%A1%E3%83%8B%E3%83%A5%E3%83%BC%E3%82%92%E4%BD%9C%E6%88%90%E3%81%99%E3%82%8B)
    - [目次](#%E7%9B%AE%E6%AC%A1)
    - [切り替えメニューの作成](#%E5%88%87%E3%82%8A%E6%9B%BF%E3%81%88%E3%83%A1%E3%83%8B%E3%83%A5%E3%83%BC%E3%81%AE%E4%BD%9C%E6%88%90)
        - [Avatar Menu Createrのウィンドウを表示する](#avatar-menu-creater%E3%81%AE%E3%82%A6%E3%82%A3%E3%83%B3%E3%83%89%E3%82%A6%E3%82%92%E8%A1%A8%E7%A4%BA%E3%81%99%E3%82%8B)
        - [アバターの指定](#%E3%82%A2%E3%83%90%E3%82%BF%E3%83%BC%E3%81%AE%E6%8C%87%E5%AE%9A)
        - [操作したいオブジェクトの選択](#%E6%93%8D%E4%BD%9C%E3%81%97%E3%81%9F%E3%81%84%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E3%81%AE%E9%81%B8%E6%8A%9E)
        - [メニューの設定](#%E3%83%A1%E3%83%8B%E3%83%A5%E3%83%BC%E3%81%AE%E8%A8%AD%E5%AE%9A)
            - [メニューの種類](#%E3%83%A1%E3%83%8B%E3%83%A5%E3%83%BC%E3%81%AE%E7%A8%AE%E9%A1%9E)
            - [アイコン](#%E3%82%A2%E3%82%A4%E3%82%B3%E3%83%B3)
            - [パラメーター初期値](#%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC%E5%88%9D%E6%9C%9F%E5%80%A4)
            - [パラメーター保存](#%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC%E4%BF%9D%E5%AD%98)
            - [オブジェクトの設定](#%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A)
            - [名前](#%E5%90%8D%E5%89%8D)
        - [メニューの作成](#%E3%83%A1%E3%83%8B%E3%83%A5%E3%83%BC%E3%81%AE%E4%BD%9C%E6%88%90)
        - [動作確認](#%E5%8B%95%E4%BD%9C%E7%A2%BA%E8%AA%8D)
        - [メニューオブジェクト作成後に設定やオブジェクトの追加と削除を行う](#%E3%83%A1%E3%83%8B%E3%83%A5%E3%83%BC%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E4%BD%9C%E6%88%90%E5%BE%8C%E3%81%AB%E8%A8%AD%E5%AE%9A%E3%82%84%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E3%81%AE%E8%BF%BD%E5%8A%A0%E3%81%A8%E5%89%8A%E9%99%A4%E3%82%92%E8%A1%8C%E3%81%86)
            - [オブジェクトの選択](#%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E3%81%AE%E9%81%B8%E6%8A%9E)
            - [設定の変更](#%E8%A8%AD%E5%AE%9A%E3%81%AE%E5%A4%89%E6%9B%B4)

<!-- /TOC -->

## 切り替えメニューの作成

服のオブジェクトの表示非表示を切り替えるためのトグルメニューを作成する。

### Avatar Menu Createrのウィンドウを表示する

Unityのメニューから`Tools` > `Modular Avatar` > `AvatarMenuCreater for Modular Avatar`を選択してウィンドウを表示する。

![AvatarMenuCreater for Modular Avatarのメニュー](https://img.porop.top/open-AvatarMenuCreaterForMA-menu.png)

### アバターの指定

表示されたウィンドウのAvatarにメニューを追加したいアバター(VRC Avatar Descriptorコンポーネントがあるオブジェクト)を指定する。

![Avatar Menu Creater for Modular Avatarのウィンドウ](https://img.porop.top/Avatar-Menu-Creater-for-MA-initial-window.png)

### 操作したいオブジェクトの選択

アバターを指定したらメニューで操作したいオブジェクトを選択する。複数選択や後から追加することもできる。

![Avatar Menu Creater for Modular Avatarのウィンドウ](https://img.porop.top/Avatar-Menu-Creater-for-MA-select-object.png)

今回は帽子の表示・非表示を切り替えるためのメニューを作成したいので帽子のオブジェクトを選択する。

### メニューの設定

目的に合わせてメニューの設定を変更する。

![Avatar Menu Creater for Modular Avatarの設定](https://img.porop.top/Avatar-Menu-Creater-for-MA-menu-settings.png)

#### メニューの種類

今回は帽子の表示・非表示を切り替えるためのメニューを作成するので、`ON/OFF`を選択する。

#### アイコン

メニューに表示する画像を設定できる。必須ではないためNoneでもよい。

#### パラメーター初期値

初期状態でメニューをONにする設定。初期状態で帽子を表示したいのでチェックボックスにチェックを入れる。

#### パラメーター保存

アバターロード時にメニューの状態を復元するかどうかを設定できる。今回はチェックを入れておく。

#### オブジェクトの設定

メニューの状態によってオブジェクトの表示・非表示やマテリアル, シェーダーのパラメーター, ブレンドシェイプ, Transformを操作できる。今回は帽子の表示・非表示を切り替えるためにON=表示にチェックを入れる。

#### 名前

メニューの名前を指定する。今回は帽子の切り替えなので`Hat`とした。

### メニューの作成

設定が完了したら`Create!`ボタンを押してメニューを作成する。ボタンを押すとアバターのルートに設定した名前のオブジェクトが生成される。

![Avatar Menu Creater for Modular Avatarによって生成されたオブジェクト](https://img.porop.top/Avatar-Menu-Creater-for-MA-created-toggle-object.png)

### 動作確認

Gesture Managerやゲーム内で動作を確認して問題なければ完了。

![Avatar Menu Creater for Modular Avatarによって生成されたメニュー](https://img.porop.top/Avatar-Menu-Creater-for-MA-toggle-test.png)

### メニューオブジェクト作成後に設定やオブジェクトの追加と削除を行う

`Create!`ボタンを押してメニューオブジェクトを作成した後でも、メニューの設定やオブジェクトの追加・削除を行うことができる。

#### オブジェクトの選択

生成されたオブジェクトをヒエラルキーから選択する。

#### 設定の変更

インスペクターで設定を変更する。

![Avatar Menu Creater for Modular Avatarによって生成されたメニューの設定](https://img.porop.top/Avatar-Menu-Creater-for-MA-settings-inspector.png)

[戻る](./Create-Expression-Menu.md)
