# **Active Recordのモデル作成**

## **3. Active Recordのモデルを作成する**
Railsでは、Active Recordモデルを作成する際に `ApplicationRecord` クラスを継承する。

```ruby
class Book < ApplicationRecord
end
```

この `Book` モデルは `books` テーブルと対応し、各カラム（例: `id`, `title`, `author`）がモデルの属性として扱われる。

---

## **3.1 マイグレーションの作成**
データベーステーブルを作成するには、**マイグレーション** を使用する。  
以下のコマンドで `books` テーブルを作成できる。

```sh
$ bin/rails generate migration CreateBooks title:string author:string
```

### **マイグレーションの例**
```ruby
class CreateBooks < ActiveRecord::Migration[8.0]
  def change
    create_table :books do |t|
      t.string :title
      t.string :author

      t.timestamps
    end
  end
end
```

このマイグレーションにより、`books` テーブルに `id`, `title`, `author`, `created_at`, `updated_at` カラムが追加される。

---

## **3.2 名前空間付きモデル**
複数の関連モデルを整理するために、**名前空間付きモデル** を作成できる。

```sh
$ bin/rails generate model Book::Order
```

これにより、`app/models/book/order.rb` に `Book::Order` クラスが作成される。

---

## **3.3 テーブル名の管理**
名前空間を持つモデルのテーブル名は `table_name_prefix` を設定することで整理できる。

```ruby
module Book
  def self.table_name_prefix
    "book_"
  end
end
```

これにより、`Book::Order` のテーブル名が `book_orders` となる。

---

## **まとめ**
✅ `ApplicationRecord` を継承してモデルを作成  
✅ `rails generate migration` でテーブルを作成  
✅ 名前空間付きモデルを整理するには `table_name_prefix` を活用

