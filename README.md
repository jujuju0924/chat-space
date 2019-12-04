## messagesテーブル
|body|text|
|image|string|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

## Association
- belongs_to :group
- belongs_to :user

## usersテーブル
|name|string|null: false, add_index: true|
|email|string|null: false, unique: true|

## Association
- has_many :messages
- has_many :groups_users
- has_many :groups,through:group.users

## groupsテーブル
|group_name|string|null: false, unique: true

## Association
- has_many :messages
- has_many :groups_users
- has_many :groups,through:group.users
## groups_usersテーブル
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :groups_users
