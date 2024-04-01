project/
├── app/
│   ├── Http/
│   │   ├── Controllers/
│   │   │   ├── UserController.php
│   │   │   ├── OtherController.php
│   │   │   └── ...
│   ├── Models/
│   │   ├── User.php
│   │   ├── OtherModel.php
│   │   └── ...
│   ├── Repositories/
│   │   ├── UserRepository.php
│   │   ├── OtherRepository.php
│   │   └── ...
│   ├── Services/
│   │   ├── UserService.php
│   │   ├── OtherService.php
│   │   └── ...
│   └── ...
├── config/
│   ├── database.php
│   └── ...
├── database/
│   ├── migrations/
│   │   ├── 2022_01_01_create_users_table.php
│   │   └── ...
│   └── seeds/
│       ├── UserSeeder.php
│       └── ...
├── resources/
│   ├── views/
│   │   ├── user/
│   │   │   ├── index.blade.php
│   │   │   ├── show.blade.php
│   │   │   └── ...
│   │   ├── other/
│   │   └── ...
│   ├── assets/
│   └── ...
├── routes/
│   ├── web.php
│   └── ...
├── tests/
│   ├── Unit/
│   │   ├── UserRepositoryTest.php
│   │   ├── OtherRepositoryTest.php
│   │   └── ...
│   ├── Feature/
│   └── ...
├── composer.json
├── .env
├── .gitignore
└── ...
