<svelte:options tag="my-web-component" />

<script>
  import NonWebComponent from "./NonWebComponent.svelte";
  import { onMount } from "svelte";
  export let darkmode = false;
  export let name = "World";

  onMount(() => {
    let element = document.querySelector("my-web-component");
    function setShadowStyle(host, styleContent) {
      var style = document.createElement("style");
      style.innerHTML = styleContent;
      host.shadowRoot.appendChild(style);
    }

    setShadowStyle(element, "@import './build/bundle.css'");
  });
  console.log(!!darkmode);
</script>

<main>
  <div>Hello {name}!</div>
  <div>darkmode is {darkmode ? "on" : "off"}</div>
  <NonWebComponent {darkmode} />
</main>
