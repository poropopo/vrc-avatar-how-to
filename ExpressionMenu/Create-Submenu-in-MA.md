# MAによって生成されるメニューをサブメニュー内にまとめる

MA Menu Installerコンポーネントによって追加されるExpression Menuをメニューのルートではなくサブメニューにまとめる方法。  

**例**  
サブメニューにまとめる前のExpression Menu  
![サブメニューにまとめる前のメニュー](https://img.porop.top/MA-menu-before-submenu.png)

サブメニューにまとめた後のExpression Menu  
![サブメニューにまとめた後のルートメニュー](https://img.porop.top/MA-menu-after-submenu-root.png)

サブメニューの内容  
![サブメニューにまとめた後のサブメニュー](https://img.porop.top/MA-menu-after-submenu.png)

## サブメニューの作成

### サブメニュー用のオブジェクトを作成

アバターに空のオブジェクトを作成する。

![サブメニュー用のオブジェクト](https://img.porop.top/Emptry-Object-for-Submenu.png)

### サブメニュー用のオブジェクトに必要なコンポーネントをアタッチする

作成したオブジェクトに`MA Menu Installer`と`MA Menu Item`コンポーネントをアタッチする。
`MA Menu Item`を以下のように設定する。

- 表示名をサブメニューの名前に変更0
- タイプをSub Menuに設定
- サブメニュー引用元を子オブジェクトから生成に設定

![サブメニュー用のオブジェクトの設定](https://img.porop.top/MA-Submenu-Object-Settings.png)

### 子オブジェクトの追加

サブメニュー用のオブジェクトに子オブジェクトを追加する。追加した子オブジェクトに`MA Menu Install Target`コンポーネントをアタッチする。  
`MA Menu Install Target`コンポーネントのInstallerでサブメニューに移動したいオブジェクトを選択する。

**サブメニューに移動したい項目の数だけこれを繰り返す。**  
Hierarchyの状態:  
![サブメニュー用の子オブジェクト](https://img.porop.top/MA-Submenu-Child-Object.png)  

コンポーネントの設定:  
![サブメニュー用の子オブジェクトの設定](https://img.porop.top/MA-Submenu-Child-Object-Settings.png)
