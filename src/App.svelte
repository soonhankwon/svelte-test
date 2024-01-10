<script>
    import Parent from "./Parent.svelte";
    import { storeName } from './store.js'
    
    // Auto-subscription
    console.log($storeName)
    let name = 'world'
    $storeName = name
</script>

<h1>Hello {name}</h1>
<Parent name={name} />