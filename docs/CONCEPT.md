# Smart Maps Walking Tour: Concept Note
## What are the challenges
United Nations Vector Tile Toolkit (UNVT) has been successful in providing basemap in a cloud-optimized way. By enabling easy sharing, access, and processing of vector geospatial data, we can save time and costs needed to utilize geospatial information. Additionally, the cloud optimization allows for easier integration with different applications, making it commonly accessible to more people, who can then utilize geospatial information to make better decisions. This approach is also forward-looking and inclusive, ensuring that everyone can benefit from the power of open geospatial information.

<details>
<summary>ja</summary>
国連ベクトルタイルツールキットを通じ、我々はベクトル形式のベースマップ情報をクラウド最適化することに成功しました。
ベクトル形式の地理空間情報を容易に共有、アクセス、処理できるようにすることで、
地理空間情報を活用するために必要な時間やコストを節約することができます。
また、クラウド最適化により、より簡単に使えて、多くのアプリケーションに結合できる用になるので、
より多くの人々が地理空間情報を活用し、より良い意思決定をすることができます。
</details>

国連ベクトルタイルツールキットを配備するに当たっても、サーバーの取得と設定は頭痛の種でした。
クラウド最適化された地理空間情報の場合、サーバー側の動的処理は複雑ではありませんが、
安価で大容量で柔軟なストレージを機動的に用意することができれば、さらにタイムリーな地理空間情報を
共有することができるようになります。



加えて、UAVやLiDARによる写真や三次元点群データ、施設管理やスマートシティに関連する三次元都市モデルが
次々にアクセス可能になりつつあります。これらのデータはベクトル形式のベースマップ情報よりもはるかに大きく、
より革新的なストレージ技術を用いなければサーバーの問題が地理空間情報の活用を阻害することになりかねません。

## Introduction of the basic idea, pros and cons
分散ウェブのアイディアは、Web3というキーワードとともに、新たな実装を得ています。
惑星間ファイルシステムは、比較的安定して高速で、またセキュリティにも考慮された分散ウェブの実装です。
クラウド最適化した地理空間情報を惑星間ファイルシステムを用いて共有するというアイディアは、
惑星間ファイルシステムとの出会いから始まりました。

Smart Maps Bazaar は、クラウド最適化された地理空間情報を惑星間ファイルシステムに記録し、
オープンにアクセス可能なように設置したゲートウェイを通じてアプリケーションに共有するという基本的アイディアです。

実装においては、オープンにアクセス可能にしたクラウド最適化可能なファイル共有のための
惑星間ファイルシステムゲートウェイを、Smart Maps Bazaar と呼んでいます。

Smart Maps Bazaar にクラウド最適化した地理空間情報を出品したい時には、
地理空間情報を自分の惑星間ファイルシステムノードに追加して、得られたコンテンツ識別子を
アプリケーションと共有すれば良いのです。

このアイディアの利点は、情報共有のために必要なノードを必要なだけ安価にすることができることです。
共有する地理空間情報が莫大になればなるほど、個別の地理空間情報に対するアクセス速度の要求が低くなる
場合があります。アクセス速度の要求が低いデータに対して相応の安価なストレージを割り当てることができる可能性が
あります。

また、惑星間ファイルシステムには pin の概念があります。自分のノードに pin しておけば、
データを手元に持っておくことになるので、オフラインでの持ち運びが実現できる可能性があります。
これは、端末や拠点においてアクセスを高速にするためのキャッシュとしても働く可能性があります。

このアイディアの課題は、アクセス制限の概念を実装する確立された方法がまだないことです。
当面、Smart Maps Bazaar のアイディアは、既存のオープンデータか、unclassified のデータに
対して適用するにとどめた方が良いでしょう。他方で、そういった unclassified のデータは
膨大であることも多く、unclassified のデータに適用するだけでも、コスト低減を実現できる可能性はあります。

## Demos (point cloud, city models, vector tiles, and imagery) with a little bit more technical details.
このセミナーは、Walking Tour という名前を持っています。実際の Bazaar でもそこで買い物を楽しむ
Walking Tour が開かれていることがあるように、このセミナーでも、実際に地理空間情報を消費していただく
Walking Tour のパートを用意します。

Tour の中で、個別のデータ形式に依存した技術的詳細についても説明します。

## Possible practical scenarios.
DWG 7 でも、Smart Maps Bazaar を Raspberry Pi 4B を用いて実現しています。
可能な実用的シナリオには、拠点内部にノードを置くことを含みます。
拠点内部のノードは、拠点固有のデータを共有することに使われるかもしれませんし、
グローバルサービスセンターから供給される共通データをキャッシュすることに使われるかも
しれません。惑星間ファイルシステムはコンテンツアドレッシングシステムなので、データの重複は自動的に排除されます。

## What is the advantage of using Smart Maps Bazaar?
Smart Maps Bazaar を利用することの利点は次のものを含むでしょう。

- サーバー環境やストレージ要求に対する柔軟性の導入
- コンテンツアドレッシングシステムの活用による情報の重複回避とキャッシュ促進
- 統一的なインタフェースの使用によるシステム構成の共通化と単純化
- 組織内利用と対外公開のインタフェースの共通化
  - 組織内利用のユーザエクスペリエンスの向上
  - パートナーシップの活性化

## Next steps
Smart Maps Bazaar は、まだ実験的なソフトウェアである惑星間ファイルシステムを使って、オープンであるが
膨大な地理空間情報をクラウド最適化した方法で共有する仕組みです。

このような仕組みを活用することにメリットがある人々の努力を結集し、この技術の開発を加速することに繋げることが、
次のステップになります。

## Invitation
我々 DWG 7 メンバーは、UN Open GIS Initiative や UN Geospatial Network に参加する国連スタッフや、
Smart Maps Bazaar のコンセプトに共感する貢献者にに対し、
Smart Maps Bazaar のコンセプトを紹介し、実際に動作する具体的なウェブ地図を見せることで、
このコンセプトのために努力を結集する方法について率直で建設的な議論を行うことを提案します。