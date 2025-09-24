<template>
  <div class="app-container">
    <div class="card shadow-lg p-4">
      <div class="Primeira" >  
      <h1 class="mb-4 text-center">Cadastro de Medidas</h1>

      
      <form @submit.prevent="adicionarMedida">
        <div class="row g-3 align-items-center">
          <div class="col-md-4">
            <input
              type="text"
              v-model="novaMedida.nome"
              class="form-control"
              placeholder="(ex: Cintura,Busto,Quadril)"
              required
            />
          </div>
          <div class="col-md-3">
            <input
              type="number"
              step="0.01"
              v-model="novaMedida.valor"
              class="form-control"
              placeholder="Valor"
              required
            />
          </div>
          <div class="col-md-3">
            <select v-model="novaMedida.unidade" class="form-select" required>
              <option value="" disabled>Unidade de Medida</option>
              <option value="m">m</option>
              <option value="cm">cm</option>
              <option value="mm">mm</option>
              
            </select>
          </div>
          <div class="col-md-2 d-grid">
            <button type="submit" class="btn btn-primary">Adicionar</button>
          </div>
        </div>
      </form>
    </div>
      
      <div class="table-responsive mt-4">
        <table v-if="medidas.length" class="table table-striped table-bordered text-center">
          <thead class="table-dark">
            <tr>
              <th>#</th>
              <th>Nome</th>
              <th>Valor</th>
              <th>Unidade</th>
              <th></th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(medida, index) in medidas" :key="index">
              <td>{{ index + 1 }}</td>
              <td>{{ medida.nome }}</td>
              <td>{{ medida.valor }}</td>
              <td>{{ medida.unidade }}</td>
              <td>
                <button
                  class="botao"
                  @click="removerMedida(index)"
                >
                  Remover
                </button>
              </td>
            </tr>
          </tbody>
        </table>

        <p v-else class="text-muted text-center mt-3">
          Nenhuma medida cadastrada.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      novaMedida: { nome: "", valor: "", unidade: "" },
      medidas: [],
    };
  },
  methods: {
    adicionarMedida() {
      this.medidas.push({ ...this.novaMedida });
      this.novaMedida = { nome: "", valor: "", unidade: "" }; // limpa o formulário
    },
    removerMedida(index) {
      this.medidas.splice(index, 1);
    },
  },
};
</script>

<style scoped>
.app-container {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  min-height: 100vh;
  background-color: #f5e9f6;
  padding: 90px;
  overflow-x: auto;
}

.card {
  width: 100%;
  max-width: 80%;
  border-radius: 50px;
  overflow-x: auto;
  background-color: #fef4ff;
   
}
.Primeira {
font-family: 'Courier New', Courier, monospace; 
}
.table-responsive {
    max-width: 100%;
}
.btn {
    background-color: rgb(80, 80, 80);
}
.table-responsive {
    font-family: initial;
    border-collapse: collapse;
}
</style>
