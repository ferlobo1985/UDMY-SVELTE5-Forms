<script>
  let name = $state('');
  let age = $state(0);
  let terms = $state(true);
  let newsletter = $state([]);
  let country = $state('')

  function validate(){
    if(name.length < 3){
      console.log(name,'Name must be at least 3 char long')
    }else{
      console.log('Name is valid')
    }
  }

  function handleSubmit(e){
    e.preventDefault();
    // VALIDATION

    console.log('SUBMIT FORM')
  }

  //$inspect(name,age,terms,newsletter,country)
</script>

<div class="container">
<form onsubmit={handleSubmit}>

  <h1>My form</h1>

  <div class="mb-3">
    <label for="name">Name</label>
    <input type="text" bind:value={name} class="form-control"
      oninput={()=> validate()}
    />
  </div>

  <div class="mb-3">
    <label for="age">Age</label>
    <input type="number" bind:value={age} class="form-control"/>
  </div>

   <div class="mb-3">
    <label for="terms">Terms</label>
    <input type="checkbox" bind:checked={terms} class="form-check-input"/>
  </div>

  <h3>Sub to newsletter ?</h3>
  <div class="form-check">
    <input type="checkbox" class="form-check-input" name="newsletter" value="yes" bind:group={newsletter}/>
    <label class="form-check-label" for="newsletter">Yes</label>
  </div>
  <div class="form-check">
    <input type="checkbox" class="form-check-input" name="newsletter" value="no" bind:group={newsletter}/>
    <label class="form-check-label" for="newsletter">No</label>
  </div>

  <div class="mb-3">
    <label for="country">Country</label>
    <select class="form-select" bind:value={country}>
      <option value="">Select a country</option>
      <option value="fr">France</option>
      <option value="usa">USA</option>
      <option value="mx">Mexico</option>
    </select>
  </div>

  <button type="submit" class="btn btn-primary mb-3">Submit</button>

</form>
</div>