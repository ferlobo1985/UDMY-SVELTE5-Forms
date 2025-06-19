<script>
  let name = $state('');
  let age = $state(0);

  $inspect(name,age)
</script>

<div class="container">
  <h1>My form</h1>

  <div class="mb-3">
    <label for="name">Name</label>
    <input type="text" bind:value={name} class="form-control"/>
  </div>

  <div class="mb-3">
    <label for="age">Age</label>
    <input type="number" bind:value={age} class="form-control"/>
  </div>
</div>