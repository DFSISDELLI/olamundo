<template>
  <v-card>
    <v-card-title>
      index
      <v-spacer/>
      <v-btn to="frutas/novo">
        ADD
      </v-btn>
    </v-card-title>
    <v-data-table
      :headers="cabecalho"
      :items="itens"
    >
      <template #[`item.actions`]="{ item }">
        <v-icon
          class="mr-2"
          small
          @click.stop="$router.push(`/frutas/${item.id}`)"
        >
          mdi-pencil
        </v-icon>
        <v-icon
          small
        >
        mdi-delete
      </v-icon>
      </template>
    </v-data-table>
  </v-card>
</template>

<script>
export default {
  name: 'IndexFrutas',
  data: () => ({
    cabecalho: [{
      text: 'Descrição',
      value: 'descricao'
    }, {
      text: 'Cor',
      value: 'cor'
    }, {
      text: 'Acoes',
      value: 'actions'
    }],
    itens: []
  }),
  mounted () {
    this.itens = [{
      id: 1,
      descricao: 'maça',
      cor: 'azul'
    }, {
      id: 2,
      descricao: 'morango',
      cor: 'vermelho'
    }]
  }
}
</script>
