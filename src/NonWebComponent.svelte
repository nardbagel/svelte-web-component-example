<script>
  export let darkmode = false;
</script>

<div class:darkmode class:lightmode={!darkmode}>
  {`you are ${darkmode ? "" : "not "} hardcore`}
</div>

<style>
  .darkmode {
    background-color: #303030;
    color: white;
  }
  .lightmode {
    background-color: white;
    color: #303030;
  }
</style>
