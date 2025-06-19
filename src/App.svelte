<script>
  import {createForm } from 'felte'
  import { validator } from '@felte/validator-yup'
  import * as yup from 'yup';

  const schema = yup.object({
    name:yup.string().required("Name is required"),
    age:yup.number().required("Age is required").min(18,"You must be at least 18")
  })

  const { form, errors } = createForm({
    onSubmit: (values,context) => {
      console.log(values)
    },
    extend: validator({schema})
  })

</script>

<div class="container">
  <form use:form>
    <h1>My form</h1>

    <div class="mb-3">
      <label for="name">Name</label>
      <input type="text" class="form-control" name="name"/>
      {#if $errors.name}
        <div class="alert alert-danger mt-2">
          {$errors.name}
        </div>
      {/if}
    </div>

    <div class="mb-3">
      <label for="age">Age</label>
      <input type="number" class="form-control" name="age"/>
       {#if $errors.age}
        <div class="alert alert-danger mt-2">
          {$errors.age}
        </div>
      {/if}
    </div>
    <button type="submit" class="btn btn-primary mb-3">Submit</button>

  </form>
</div>