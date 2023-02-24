<template>
  <div class="container">
    <div class="row">
        <div class="col-md-7 mrgnbtm">
        <h2>Crear Usuario</h2>
            <form>
                <div class="row">
                    <div class="form-group col-md-6">
                        <label htmlFor="exampleInputEmail1">Nombre</label>
                        <input type="text" class="form-control" v-model="firstName" name="firstname" id="firstname" aria-describedby="emailHelp" placeholder="Nombre" />
                    </div>
                    <div class="form-group col-md-6">
                        <label htmlFor="exampleInputPassword1">Apellido</label>
                        <input type="text" class="form-control" v-model="lastName" name="lastname" id="lastname" placeholder="Apellido" />
                    </div>
                </div>
                <div class="row">
                    <div class="form-group col-md-12">
                        <label htmlFor="exampleInputEmail1">Correo electrónico</label>
                        <input type="text" class="form-control" v-model="email" name="email" id="email" aria-describedby="emailHelp" placeholder="Email" />
                    </div>
                </div>
                <button type="button" @click='createUser()' class="btn btn-danger">Crear</button>
            </form>
        </div>
    </div>
    </div>
</template>

<script>
export default {
  name: 'Crear Usuario',
  data() {
    return {
      firstName: '',
      lastName: '',
      email: ''
    }
  },
  methods: {
      createUser() {
          console.log(this.firstName)
          const payload = {
              firstName: this.firstName,
              lastName: this.lastName,
              email: this.email
          }
          this.$emit('createUser', payload)
          this.clearForm();
      },
      clearForm() {
          this.firstName = "";
          this.lastName = "";
          this.email = "";
      }
  }
}
</script>