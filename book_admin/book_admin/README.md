# パーフェクト Ruby on Rails

## Ruby on Rails と MVC

### コールバックによる制御

- レコードを作成して、保存する一連の流れの間のさまざまな箇所で任意の処理を差し込める
  - 特定の処理に引っ掛けて別の処理を呼ぶことをコールバックと呼ぶ

e.g.)

```ruby
before_validation :add_lovely_to_cat

def add_lovely_to_cat
  self.name = self.name.gsub(/Cat/) do |matched|
    "lovely #{matched}"
  end
end
```

### ActiveRecord::Enum で列挙型を扱う

- enum 型は数値のカラムに対してプログラム上で扱える別名を与える
  e.g.)

```ruby
enum sales_status: {
  reservation: 0, # 予約受付
  now_on_sale: 1, # 発売中
  end_of_print: 2 # 販売終了
}
```
