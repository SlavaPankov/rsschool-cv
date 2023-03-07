[rsschool-cv](https://slavapankov.github.io/rsschool-cv/)

___

# Pankov Svyatoslav

___

## My Contacts:

- Phone: +7 (705)-865-74-99;
- Email: [SlavaPank94@yandex.ru](mailto:SlavaPank94@yandex.ru) ([pankovslava94@gmail.com](mailto:pankovslava94@gmail.com));
- Telegram: [SlavaPankov](https://t.me/SlavaPankov);
- GitHub: [SlavaPankov](https://github.com/SlavaPankov/);
- Diskord: SlavaPankov(@SlavaPankov);

___

## About me:

I graduated from the Nidegorod Technical University, bachelor's degree. I joined IT a little over a year ago. I was fascinated by web development, and specifically front-end, because I want to create things that people enjoy. 
I started by studying the profession in Skillbox courses. Studied weblayout, basic JS. Six months later, I received the first offer at an Internet marketing agency. But the learning and development did not stop there. I started learning React in Vue, also learned native PHP. 
I eagerly absorb new information for myself and try to develop as a competent specialist. And now I work as a business process developer.
My goal here is to consolidate my knowledge, as well as meet people to exchange experience.

___

## My skills: 

### Hard skills:

- HTML;
- CSS (Preprocessors SASS/LESS);
- JS (Intermediate);
- Webpack, Gulp;
- React JS (Begginer);
- Vue (Begginer);
- PHP (Native);
- Git;
- VSCode, PHPStorm;
- Scrum;
- BEM

### Soft skills:

- High learning;
- Time menagment;
- Proactivity;
- Teamwork;
- Adaptability;
- Critical thinking;

## Code example:

```javascript

/* 
  Метод возвращает заданное количество названий месяцев в обратном порядке, начиная с текущего месяца 
  (vars слобальная константа, которая содержит названия месяцев)
*/

months(config) {
  const values = [];
  const date = new Date();
  let currentMonth = date.getMonth();
  let flag = true;

  for (let i = currentMonth; i >= currentMonth - config.count; i--) {
    values.push(vars.month[i]);
    if (i - config.count < 0 && flag) {
      i = config.count;
      flag = false
    }

    if (values.length > config.count) {
      break;
    }
  }

  return values;
}

```

## My projects:

- [Coin](https://github.com/SlavaPankov/coin-vue) - This is Vue 3 project. I made simplified banking operations with cryptocurrencies. This project is at the stage of code refactoring.

- [Technozavr](https://github.com/SlavaPankov/Technozavr) - This is also Vue 3 project. I made an online store.

- [pravoNN](https://github.com/SlavaPankov/pravoNN) - This project is a commercial order. Adaptive, crossbrowsers weblayout. The project uses gulp, BEM, SCSS. Some libraries: Swiper.js, inputmask, just-validate. And also I made send emails with "phpmailer"