# DB設計

### users テーブル

|  Column                |  Type    |   Options   |
|------------------------|----------|-------------|
|   email                |  string  | null: false |
|   excerpted_password   |  string  | null: false |
|   nickname             |  string  | null: false |
|   lust_name            |  string  | null: false |
|  first_name            |  string  | null: false |
| lust_name_kana         |  string  | null: false |
| first_name_kana        |  string  | null: false |
|   birth_date           |   date   | null: false |

### Association
- belongs_to :items
- belongs_to :orders


## items テーブル

|   Column         |   Type     |   Options         |
|------------------|------------|-------------------|
|    user          | references | foreign_key: true |
|    name          | string     |    null: false    |
|  description     |    text    |    null: false    |
|  category_id     |  integer   |    null: false    |
| condition_id     |  integer   |    null: false    |
| postage_payer_id | references | foreign_key: true |
| prefecture_id    | references | foreign_key: true |
|  handling_id     | references | foreign_key: true |
|   price          | references | foreign_key: true |


### Association
- belongs_to :users

## orders テーブル

|  Column |    Type     |   Options                    |
|---------|-------------|------------------------------|
|  item   | references  | foreign_key: true            |
|  user   | references  | foreign_key: true            |

### Association
* has_one :users
- belongs_to :items


### addresses テーブル
|  Column         |    Type   | Options          |
|-----------------|-----------|------------------|
|  post_code      |  string   | null: false      |
|  building_name  |  string   |                  |
|  phone_number   |  string   | null: false      |
|  prefectures_id |  integer  | null: false      |
|  city           |  integer  | null: false      |
|  purchase       | references| foreign_ker: true|


### Association
-belongs_to :order