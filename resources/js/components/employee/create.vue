<template>
  <section class="content">
    <div class="container-fluid">
      <div class="row mb-2">
        <!-- <div class="col-sm-6">
            <h1>Add Employee</h1>
          </div>
          <div class="col-sm-6">
            <ol class="breadcrumb float-sm-right">
              <li class="breadcrumb-item"><a href="#">Home</a></li>
              <li class="breadcrumb-item active">General Form</li>
            </ol>
        </div>-->
      </div>
    </div>
    <div class="container-fluid">
      <div class="row justify-content-center">
        <!-- left column -->
        <div class="col-md-8">
          <!-- general form elements -->
          <div class="card card-secondary">
            <div class="card-header">
              <h3 class="card-title">Add Employee</h3>
            </div>
            <!-- /.card-header -->
            <!-- form start -->
            <form>
              <div class="card-body">
                <div class="row">
                  <div class="col-6">
                    <div class="form-group">
                      <label>Name</label>
                      <input type="text" class="form-control" v-model="form.name" />
                      <small class="text-danger" v-if="errors.name">{{errors.name[0]}}</small>
                    </div>
                  </div>
                  <div class="col-6">
                    <div class="form-group">
                      <label>Email</label>
                      <input type="email" class="form-control" v-model="form.email" />
                    </div>
                    <small class="text-danger" v-if="errors.email">{{errors.email[0]}}</small>
                  </div>
                </div>
                <div class="row">
                  <div class="col-6">
                    <div class="form-group">
                      <label>Salary</label>
                      <input type="text" class="form-control" v-model="form.salary" />
                    </div>
                    <small class="text-danger" v-if="errors.salary">{{errors.salary[0]}}</small>
                  </div>
                  <div class="col-6">
                    <div class="form-group">
                      <label>Address</label>
                      <input type="text" class="form-control" v-model="form.address" />
                    </div>
                    <small class="text-danger" v-if="errors.address">{{errors.address[0]}}</small>
                  </div>
                </div>
                <div class="row">
                  <div class="col-6">
                    <div class="form-group">
                      <label>NID Number</label>
                      <input type="text" class="form-control" v-model="form.nid" />
                    </div>
                    <small class="text-danger" v-if="errors.nid">{{errors.nid[0]}}</small>
                  </div>
                  <div class="col-6">
                    <div class="form-group">
                      <label>Joining Date</label>
                      <input type="date" class="form-control" v-model="form.joiningDate" />
                    </div>
                    <small class="text-danger" v-if="errors.joiningDate">{{errors.joiningDate[0]}}</small>
                  </div>
                </div>
                <div class="row">
                  <div class="col-6">
                    <div class="form-group">
                      <label>Image</label>
                      <input type="file" class="form-control" @change="onfileSelected"/>
                    </div>
                    <small class="text-danger" v-if="errors.image">{{errors.image[0]}}</small>
                  </div>
                  <div class="col-6">
                    <img :src="form.image" style="height:30px; width:40px;">
                  </div>
                </div>
              </div>
              <div class="card-footer">
                <button type="submit" class="btn btn-primary float-right">Submit</button>
              </div>
            </form>
          </div>
        </div>
      </div>
      <!-- /.row -->
    </div>
    <!-- /.container-fluid -->
  </section>
</template>
<script>
export default {
  mounted() {
    if (!User.loggedIn()) {
      this.$router.push({ name: "/" });
    }
  },
  data() {
    return {
      form: {
        name: null,
        email: null,
        salary: null,
        address: null,
        nid: null,
        joiningDate: null,
        image: null,
      },
      errors: {}
    };
  },
  methods: {
    onfileSelected(event){
     let file=event.target.files[0]
     if(file.size >1048770 ){
      Notification.imageValidation();
     }else{
      let reader = new FileReader
     }
    },
    signup() {
      
    }
  }
};
</script>