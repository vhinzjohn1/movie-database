<script>
    let inputValue = '';
</script>

<form class="search-container">

  <input bind:value={inputValue} type="text" id="search-bar" placeholder="Search Movie" />
  <a href="#" class="icon-wrapper"
    ><img
      class="search-icon"
      alt="icon"
      src="http://www.endlessicons.com/wp-content/uploads/2012/12/search-icon.png"
    /></a
  >
</form>

<style>
  .search-container {
    position: relative;
    width: 240px;
    margin-right: 3rem;
  }

  input#search-bar {
    border-radius: 1rem;
    width: 100%;
    height: 45px;
    padding: 0 20px;
    font-size: 1rem;
    border: 1px solid #d0cfce;
    outline: none;
    &:focus {
      border: 1px solid #000000;
      transition: 0.35s ease;
      color: #008abf;
      &::-webkit-input-placeholder {
        transition: opacity 0.45s ease;
        opacity: 0;
      }
      &::-moz-placeholder {
        transition: opacity 0.45s ease;
        opacity: 0;
      }
      &:-ms-placeholder {
        transition: opacity 0.45s ease;
        opacity: 0;
      }
    }
  }

  .search-icon {
    position: absolute;
    height: 50px;
    width: 50px;
    top: 0;
    right: -40px;
  }
</style>
