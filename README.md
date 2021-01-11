#テーブル設計

##users テーブル

| Column     | Type        | Option       |
|:-----------|------------:|:------------:|
| name       | string      | null: false  |
| email      | string      | null: false  |
| password   | string      | null: false  |

###Association
-has_many :room_users
-has_many :message
-has_many :rooms, thorough: room_users


##roomテーブル

| Column     | Type        | Option       |
|:-----------|------------:|:------------:|
| name       | string      | null: false  |

###Association
-has_many :messages
-has_many :users,thorough: room_users
-has_many :room_users
##room_userテーブル

| Column     | Type        | Option                         |
|:-----------|------------:|:------------------------------:|
| user       | references  | null: false,foreign_key: true  |
| room       | references  | null: false,foreign_key: true  |

###Association

belongs_to  :room
belongs_to  :user

##messagesテーブル

 Column     | Type         | Option                            |
|:-----------|------------:|:--------------------------------:|
| content    | string      | null: false ,foreign_key: true   | 
| user       |references   | null: false, foreign_key: true  |
| room       | references  | null: false, foreign_key:true|

###Association
belongs_to :room
belongs_to :user
 



