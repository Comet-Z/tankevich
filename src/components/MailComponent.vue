<template>
  <v-card
    class="mx-auto"
    width="100%"
    height="100%"
  >
    <v-toolbar
      color="pink"
      dark
    >
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>Почта</v-toolbar-title>

      <v-spacer></v-spacer>

   <v-card-title>
      <v-text-field
        v-model="search"
        append-icon="mdi-magnify"
        label="Search"
        single-line
        hide-details
      ></v-text-field>
    </v-card-title>
    </v-toolbar>

    <v-list dark two-line>
      <v-list-item-group
        v-model="selected"
        active-class="pink--text"
        multiple
      >
        <template v-for="(item, index) in items">
          <v-list-item :key="item.title">
            <template v-slot:default="{ active }">
              <v-list-item-content>
                <v-list-item-title v-text="item.title"></v-list-item-title>

                <v-list-item-subtitle
                  class="text--primary"
                  v-text="item.headline"
                ></v-list-item-subtitle>

                <v-list-item-subtitle v-text="item.subtitle"></v-list-item-subtitle>
              </v-list-item-content>

              <v-list-item-action>
                <v-list-item-action-text v-text="item.action"></v-list-item-action-text>

                <v-icon
                  v-if="!active"
                  color="grey lighten-1"
                >
                  mdi-star-outline
                </v-icon>

                <v-icon
                  v-else
                  color="yellow darken-3"
                >
                  mdi-star
                </v-icon>
              </v-list-item-action>
            </template>
          </v-list-item>

          <v-divider
            v-if="index < items.length - 1"
            :key="index"
          ></v-divider>
        </template>
      </v-list-item-group>
    </v-list>
  </v-card>
</template>

<script>
  export default {
    data: () => ({
      search: '',
      selected: [2],
      items: [
        {
          action: '15 мин. назад',
          headline: 'Когда встретимся?',
          subtitle: `Привет, хотел узнать когда мы сможем встретится и во сколько?`,
          title: 'Максим Демиденко',
        },
        {
          action: '2 часа назад',
          headline: 'Вечеринка',
          subtitle: `Кто ещё будет с нами?`,
          title: 'вы, Дмитрий Парфенцов',
        },
        {
          action: '6 часов назад',
          headline: 'Путешествие',
          subtitle: 'Есть рекомендации куда можно съездить в Париже?',
          title: 'Виктория Дмитриевна',
        },
        {
          action: '12 часов назад',
          headline: 'Подарок на ДР',
          subtitle: 'Что думаешь ей подарить?',
          title: 'Алексей Шевцов',
        },
        {
          action: '18 часов назад',
          headline: 'Отпуск',
          subtitle: 'Когда ты там планировал сделать отпуск?',
          title: 'Дмитрий Терлеев',
        },
        {
          action: '24 часа назад',
          headline: 'Вечерняя встреча',
          subtitle: 'Спасибо что составил компанию!',
          title: 'Кирилл Лейченок',
        },
        {
          action: '1д назад',
          headline: 'Работа',
          subtitle: 'Жду тебя с утра, как обычно. Кое-что обсудим.',
          title: 'Босс',
        },
        {
          action: '2д назад',
          headline: 'Свидание',
          subtitle: 'Куда думаешь сходить?',
          title: 'Нина Алёшина',
        },
        {
          action: '4д назад',
          headline: 'Дедлайн к работе',
          subtitle: 'Там сказали, что он где-то между сентябрём и августом',
          title: 'Артём Павлов',
        },
      ],
    }),
  }
</script>

<style>

</style>