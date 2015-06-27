# Faker zh_TW Provider

Currently [Faker](https://github.com/fzaninotto/Faker) has a [zh_TW provider](https://github.com/fzaninotto/Faker/tree/master/src/Faker/Provider/zh_TW) but still not release in newest stable version.

If we want to use zh_TW provider but do not hope to load unstable packages, we can use this repository instead, until Faker release a new version.

The source was created by [Tz-Huan Huang](https://github.com/tzhuan)

2015-02-22

## How To Use

``` php
$faker = \Faker\Factory::create('zh_TW');

$faker->addProvider(new \Faker\Provider\zh_TW\Address($faker));
$faker->addProvider(new \Faker\Provider\zh_TW\Company($faker));
$faker->addProvider(new \Faker\Provider\zh_TW\Person($faker));
$faker->addProvider(new \Faker\Provider\zh_TW\PhoneNumber($faker));
$faker->addProvider(new \Faker\Provider\zh_TW\Text($faker));

foreach (range(1, 50) as $i)
{
	$data['name'] = $faker->name;
	$data['username'] = $faker->username;
	$data['password'] = password_hash('pass');
	$data['email'] = $faker->email;
	$data['nick'] = $faker->firstName;
	$data['mobile'] = $faker->phoneNumber;
	$data['phone'] = $faker->phoneNumber;
	$data['address'] = $faker->address;
	$data['organization'] = $faker->company;
	$data['title'] = $faker->title;
	$data['state'] = $faker->randomElement([1,1,1,0]);
	$data['registered'] = $faker->dateTime->format('Y-m-d H:s:i');
	$data['last_login'] = $faker->dateTime->format('Y-m-d H:s:i');

	$this->db->getWriter()->insertOne('users', $data);
}
```

## Installation

``` json
{
	"require": {
		"asika/faker-zhtw": "*@stable"
	}
}
```
