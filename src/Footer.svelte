<script>
  let year = new Date().getFullYear();
  export let legal =
    "Copyright © " + year + " Tom Foolery. All Rights reserved.";
  export let attribution = "Tom Foolery";
  export let attrLink = "https://mehder.com/";
</script>

<footer>
  <p>{legal}</p>
  <p>
    Developed by
    <a href={attrLink} target="_blank">{attribution}</a>
  </p>
</footer>

<style>
  footer {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
    background-color: #222;
    color: white;
  }
  p {
    margin: 2em;
  }
  a {
    color: darkorange;
    text-decoration: none;
    font-weight: bold;
    font-size: 16px;
  }
  a:hover {
    text-decoration: underline;
  }
</style>
