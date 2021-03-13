# ProtoSpace 


## usersテーブル
| column     | Type    | Options
|------------------------------------------------------------
| email      | string  | Null: false
| password   | string  | Null: false
| name       | string  | Null: false
| profile    | text    | Null: false
| occupation | text    | Null: false
| position   | text    | Null: false

### Association
- has_many :prototypes
- has_many :comments


## prototypeテーブル
| column     | Type      | Options
|-------------------------------------------------------------
| title      | string    | Null: false
| catch_copy | text      | Null: false
| concept    | text      | Null: false
| image      |           | ActiveStorageで実装
| user       | reference | 

### Association
- belongs_to :users
- has_many   :comments
- has_one_attached :image


## comments
| column     | Type      | Options
|-------------------------------------------------------------
| text       | text      | Null: false
| user       | reference |
| prototype  | reference | 

### Association
- belongs_to :users
- belongs_to :prototype