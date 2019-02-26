<template>
    <div class="hello">
        <h1>
            Mensagem Enviada : {{ msg }}
        </h1>
    </div>
</template>



<script>
export default {
    name: 'FirstComponent',
    props: {
        msg: String
    },
    data: {
        message: 'Hello World!',
    },
    created: function(){
        
    }
}
</script>
