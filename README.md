'example-sql-custom' => [
        'sqlauthcustom:SQL',
        'dsn' => "mysql:host=$DB_HOST;port=$DB_PORT;dbname=$DB_DATABASE",
        'username' => $DB_USERNAME,
        'password' => $DB_PASSWORD,
        'query' => 'SELECT **fields** FROM users WHERE email = :email;',
        'password_verify' => function($rawPassword, $row){
            return password_verify($rawPassword, $row['password']);
        },
        'ignore_attributes' => ['password']
],
