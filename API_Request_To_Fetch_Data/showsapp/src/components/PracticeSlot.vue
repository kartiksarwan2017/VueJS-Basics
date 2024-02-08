<template>
   <div>
    <div class="header">
        <slot name="header"></slot>
    </div>
    <div class="body">
        <h1>Title</h1>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Reprehenderit repellat maiores sed ut facilis.</p>
        <slot></slot>
    </div>
    <div class="footer">
        <slot name="footer"></slot>
    </div>
   </div>
</template>

