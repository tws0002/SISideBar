# SISideBar
インストール

    Clone or download > Download ZIP からZIPファイルをダウンロードしてください。

    解凍したSiSideBarフォルダを C:\Program Files\Autodesk\ApplicationPlugins へコピーしてください。
    
    MayaをCドライブ以外にインストールしている場合でもSiShelfフォルダは
    C:\Program Files\Autodesk\ApplicationPlugins
    に置く必要があるようです。

    ApplicationPluginsフォルダが存在しない場合は作成してください。

    動作確認はMaya2014～2018で行っています。
    
    -----------------------------------------------------------------------------------------
    ・2013 × ツールを認識できません
    ・2014 △ ドッキングできません、平面ハンドルとのリンクができません、Uni/Volモードが不安定
    ・2015　〇 平面ハンドルとのリンクができません
    ・2016　◎ 特に問題なし
    ・2017　〇 UI周りの描画がおかしくなることがある（2017のバグかも）
    ・2018　◎ 特に問題なし
    -----------------------------------------------------------------------------------------
    
    設定ファイルは
    C:\Users\[User_Name]\Documents\maya\Scripting_Files
    に生成されます。
    不具合が発生した場合は削除してみると直るかもしれません。

    不要になった場合はフォルダを削除してください。
    
    インストールに成功するとウィンドウメニューにSiSideBarが追加されます。
    
    Readmeはこれからかくです。
    Maya起動時に前回の終了状態でウィンドウ位置、ドッキング位置を復元します。
    
![20171113-212852](https://user-images.githubusercontent.com/28256498/32726190-6982b406-c8bb-11e7-9c9d-25a018194a1a.jpg)
![2017-11-13_23h23_06](https://user-images.githubusercontent.com/28256498/32730253-d5b4e294-c8c9-11e7-9c9c-0d21e2a5c8e8.png)


主な機能
    
    ・SRT選択状態のリンク

    ・マニピュレータのXYZ軸との相互リンク

    ・SRT入力窓の再現
    ・四則演算入力のSI方式とMaya方式の両立（10+、+=10など）
    ・計算式入力対応 (1*(3+5))/25+3 とか
    ・ランダム関数入力 r→0～1, r(n)→0～n, r(n,n2)→n～n2, r(n,n2,s)シードをsで整数指定、同じシードなら同じ乱数が返ってくる
    ・リニア関数対応 l(n1, n2) ｎ1～n2の間に選択オブジェクトを均等に配置、ランダム関数、マルチライン入力との併用も可能
    ・ホイール入力への対応（Shift,Ctrlで桁調整 10, 1, 0.1）
    ・カッコ[ ]による数値追加入力に対応 通常1.0ずつ、 shift 0.1ずつ、ctrl 10ずつ
    ・スペース入力は0.0扱い
    ・コンポーネントへの入力対応
    ・3軸ボタン、を右クリックで一括入力、各XYZ軸右クリックで一括入力状態をトグル
    ・アトリビュートのロック状態の表示、ロック/アンロック一括切り替え機能
![default](https://user-images.githubusercontent.com/28256498/33526068-27f318aa-d87e-11e7-81dd-ec940fd98879.gif)
    
    
    ・マウスジェスチャー入力に対応
    入力窓をクリック＆ドラッグで数値加算できます。
    右側にドラッグすると加算、左で減算。
    SIは対角で+-、-+となってましたがわかりにくいので仕様変更。
    円を描くようにすると続けて加算できます。
    Uターンすると符号反転（+-切り替え）します。Uターン角度の閾値は現在120°
    Shiftで+-0.1、Ctrlで+-10
    
    ・オブジェクト名検索、スペース区切りで複数ワード検索可能　例）pShper* pCube*
    ・検索タイプのフィルター機能、右クリックでオプションメニューオープン
    ・コンポーネント検索 コロン区切りで連続指定、スペース区切りで複数指定 例）1:50 60:75 90
    

    ・FreezeMの再現（ヒストリをベイクしてウェイトを書き戻し、クラスタとブレンドシェイプは保護）
    ・ラティスをウェイトつけたままベイクできます
    ・ウェイトをミュートしてからFreezeMするとバインドポーズを簡単に変更できます
    ・とりあえずかけておくとメッシュにまつわる大概の不具合が解消します

    ・Freezeの再現

    ・トランスフォームスペースのリンク（Global, Local, View, Objectなど）

    ・VolモードUniモードの再現

    ・Transformメニュー再現、拡充
    ・ResetActor
    ・JointOriento↔Rotation
    ・MutchiTransform
    ・FreezeTransform
    ・ResetTransform
    ・MoveCenterToSelection
    ・RoundTransform / SRTの小数点指定桁数以下の丸め機能
    ・絶対値に移動
    ・サイドバーの軸選択状態を優先するモード
    ・ニュートラルノードの設定 / ニュートラルポーズ代替機能
    ・SRTの表示桁数設定

    ・アニメーションキーボタンをついか（右クリックで3軸一括設定）

    ・センターモードでセンターを移動

    ・Groupモードで選択したオブジェクトが属するセットを逆引き選択

    ・Clusterモードで選択したコンポーネントが属するクラスタ、セットを逆引き選択

    ・UIメニューの折り畳み
    
    ・UIカラーの切り替え

    ・MayaシーンファイルをUIへのドラッグドロップでOpenScene扱いで開けます。自動でSetProjectされます。

    ・Numpyモジュールがインストールされているとコンポーネント計算が3倍くらい早くなります
    
    ・Editにオブジェクト編集機能拡張中
    UVを保持してエッジを押し出す機能
    UIでの押し出しはUVの押し出し距離調整~縫合のタイミングを任意で指定できます。
    UIなしでの押し出しはUIでの設定をもとに縫合まで自動で行います。
    UVを完全に任意調整したい場合は押し出し距離を0に設定してください。
![2](https://user-images.githubusercontent.com/28256498/35185509-112718ba-fe49-11e7-8c75-ab29eb50143a.gif)
    

    ・とりあえず使用説明動画とってみました
https://youtu.be/14T5_Ak4dAE
https://youtu.be/Ymq6SQwWF8s
https://youtu.be/tC5p24b9sUQ
https://youtu.be/dZUoGX0SBOQ

更新履歴
    
    2018/01/20 ver2.3.2--------------------------------------------------------------------
    ・UV保持して押し出す機能追加
    2018/01/18 ver2.3.1--------------------------------------------------------------------
    ・マウスボタン毎のジェスチャー入力有効無効切り替え設定を追加
    2017/12/24 ver2.3.0--------------------------------------------------------------------
    ・セレクションフィルターの挙動を大きく修正 左クリック→シングル選択 Shilt+左クリック→追加選択/解除 右クリック→全選択
    2017/12/23 ver2.2.9--------------------------------------------------------------------
    ・フリーズトランスフォームのエラー回避
    ・ピボットをリセットしないリセットトランスフォーム追加
    2017/12/22 ver2.2.8-------------------------------------------------------------------- 
    ・Parentボタン機能追加 左クリックでいままで通りの親子付け 右クリックでローカル変換保持して親子付け 
    ・2.2.7での不具合修正 
    ・レジスターコマンド修正
    2017/12/20 ver2.2.7--------------------------------------------------------------------
    ・選択設定機能を追加
    ・UIにマウスオーバーでMayaからの情報反映機能追加
    ・セレクションフィルタの状態をMayaの状態から反映するように修正
    ・マニプの軸選択を反映する機能追加、SRTの実行がなくても選択変更に反映するように改善
    2017/12/17 ver2.2.6--------------------------------------------------------------------
    ・オブジェクトスペースのトランス設定、表示回りを大きく修正しました。 
    明示的にペアレント（ローカル）スペースと区別するようになってます。
    SI、Maya共になかった機能なんですが、きっと便利、、、なはず。
    2017/12/16 ver2.2.4--------------------------------------------------------------------
    ・ダブルクリックでエッジループ選択が効かなくなる不具合修正
    ・Match Transform とChild Comp設定の連携
    ・同ピッカーカーソル設定修正
    ・同キャンセルボタンを表示
    ・セレクションフィルターのMayaからの設定を同期表示するように改善
    2017/12/13 ver2.2.3--------------------------------------------------------------------
     ・フリーズ、リセットトランスフォームのピボットリセット修正
     ・同挙動をSI準拠に修正
    2017/12/09 ver2.2.2--------------------------------------------------------------------
     ・2017以降のニュートラルノード削除不具合対応
     ・マウスジェスチャー入力のアンドゥ履歴をマウスクリック~リリースまでで一つになるように修正
    2017/12/09 ver2.2.1--------------------------------------------------------------------
     ・ニュートラルノードをロック ・ニュートラルノードの複数編集修正
     ・Mayaパラメータ反映系を修正 ・マルチライン入力のアンドゥを1つに
     ・UIにポインタが入ったらMayaからの設定を反映 ・軸毎ロックのUI改善
     ・2017以降でニュートラルノード解除不具合→これから対応
    2017/12/09 ver2.2.0--------------------------------------------------------------------
    　・入力窓選択時にテキスト全選択されるように修正         
     ・L(ロック)ボタン右クリックで軸の個別ロック機能追加。フォーカス外れるとウィンドウ消えます。
     ・セットニュートラルノード機能追加、選択オブジェクトの親に同SRTのノードを挿入。
    2017/12/03 ver2.1.8--------------------------------------------------------------------
     ・誤字を修正 Costrain→Constrain / Handel→Handle 潤樹さんご指摘ありがとうございます。 
     ・デストロイモードの明滅を省エネ化、最初の数回だけ明滅（重要） 
     ・デストロイモードへの多段変形を実装（超重要）
    2017/12/03 ver2.1.7--------------------------------------------------------------------
     ・UIに投げ入れてOpenシーン機能の不具合修正 
     ・同機能シーンに変更がない場合はダイアログが出ないように修正 屋良Martinさん、ご指摘ありがとうございました！ 
     ・デストロイモードが明滅するように機能追加（重要）
    2017/12/03 ver2.1.6--------------------------------------------------------------------
    　・ロックのコンポネントモード時の表示修正(2.1.6)
    2017/11/29 ver2.1.5--------------------------------------------------------------------
     ・アトリビュートのロック状態の表示、ロック/アンロックをUI上からできるように機能追加
    2017/11/26 ver2.1.4--------------------------------------------------------------------
     ・トランスフォームメニューをティアオフして触ってるとメニューが消えることがあるバグを修正、2017だけ解消できずorz
    2017/11/25 ver2.1.3--------------------------------------------------------------------
     ・Maya2017以降でタブをHideしたらトランス情報取得機能が止まるバグを修正
    2017/11/23 ver2.1.2--------------------------------------------------------------------
     ・サイドバーの軸選択状態を優先するモードを追加
    2017/11/22 ver2.1.1--------------------------------------------------------------------
     ・デストロイモード解放 
     ・COG、Uni/Volモードの不具合修正
     ・絶対値に移動のチェックに不備があったので修正
     ・ホイール入力の細かい不具合修正
    2017/11/21 ver2.1.0--------------------------------------------------------------------
     ・細かい不具合対応
    2017/11/20 ver2.0.9--------------------------------------------------------------------
     ・Linear関数の実装 randam関数、マルチライン入力との併用も可能（需要あるのか？？）
     ・オブジェクトモードのセンターオブジオメトリ機能追加 
     ・Nurbs,Curveタイプへの対応が不完全だった部分を修正 
     ・2.0.8での2次バグ修正
    2017/11/19 ver2.0.8--------------------------------------------------------------------
     ・2018のコンポーネントモード仕様変更に対応
     ・2018特定の条件で落ちる不具合を修正
     ・トランスフォーム軸スペース名をMaya準拠に変更
     ・Uni/Volモードのボタンを1つに統一、代わりにCompoentボタンを挿入
    2017/11/18 ver2.0.7--------------------------------------------------------------------
     ・マウスジェスチャー入力に対応
     ・アトリビュートの表示桁数変更に対応
     ・アトリビュートの小数点丸め機能実装
     ・マルチライン入力の改善と不具合対応
    2017/11/17 ver2.0.6--------------------------------------------------------------------
     ・絶対値に移動の計算誤差修正 
     ・絶対値に移動を設定しているときのコンポーネント回転、スケールの不具合を修正
     ・基本的な計算式入力に対応（例）1+2*(10-3)/5など
     ・ランダム関数に対応 
     書式：r→0～1, r(n)→0～n, r(n,n2)→n～n2, r(n,n2,s)シードをsで整数指定、同じシードなら同じ乱数が返ってくる
     ・'[',']'　カッコによる数値入力に対応、shift, ctrlでそれぞれ0.1ずつ、10ずつの入力に
    2017/11/16 ver2.0.5--------------------------------------------------------------------
     ・絶対値に移動追加 
     ・トランスフォームメニューをローカライズ 
     ・Maya2014への対応（※ドッキングできません）
    2017/11/15 ver2.0.4--------------------------------------------------------------------
     ・2017,2018での起動時ドック状態の復元に対応 
     ・Match_Transformのバグ修正（開発環境では起きにくい特殊なバグでした…） 
    2017/11/15 ver2.0.3--------------------------------------------------------------------
     ・Trans入力で掛算割り算が効かなかったのを修正 
     ・Curve、Nurbsタイプのコンポーネント選択に対応
    2017/11/14 ver2.0.2--------------------------------------------------------------------
     ・英語版のメッセージ不具合対応 
     ・2016Extention2の起動時エラー対応  
     ・スケールUni/Volモード不具合対応 
     ・COGモードのローテーションがスペース設定によっては効かなかったのを修正
    2017/11/13 ver2.0.1--------------------------------------------------------------------
     ・入力窓にスペースを打つと0.0になるように変更
    2017/11/12 ver2.0.0 リリース
