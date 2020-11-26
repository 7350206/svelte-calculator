elements can have directives, which controls the element behavior
`on:eventname={handler}`
`on:eventname|modifiers={handler}`

let count=0
function handleClick(evt){count+=1}
<button on:click={handleClick}>{count}</button>

handlers can be inliners without no performance issues
`<button on:click={()=> count += 1}`

