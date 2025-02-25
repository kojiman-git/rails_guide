# **Active Recordの概要**

## **Active Recordとは**
**Active Record** は、**MVCのモデル（M）** の一部であり、データとビジネスロジックを扱うシステムの階層です。Railsの **Active Record** は、**オブジェクトリレーショナルマッピング（ORM）** を提供し、Rubyオブジェクトをリレーショナルデータベースと連携させます。

## **Active RecordとActive Modelの違い**
- **Active Record**: データベースと密接に結びついたORMシステム  
- **Active Model**: データベースがなくても利用できるモデルの抽象化  

## **Active Recordパターン**
- Martin Fowlerの『Patterns of Enterprise Application Architecture』で定義された設計パターン  
- データベースの行をオブジェクトとして扱い、データベースアクセスとドメインロジックを統合  

## **ORMの特徴**
- SQLを書かずにRubyオブジェクトを使ってデータの保存・取得が可能  
- データベース操作を簡潔にし、開発効率を向上  

## **Active Recordの機能**
- モデルとデータの表現  
- モデル間の関連付け（アソシエーション）  
- 継承関係の管理  
- データのバリデーション  
- オブジェクト指向的なデータベース操作  

**Active Recordを活用するには、RDBMSやSQLの理解が役立つ。**
