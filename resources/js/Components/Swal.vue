<template> 
</template>

<script>
export default {
    props: {
        errors: {
            type: Object,
            required: true
        },

        flash: {
            type: Object,
            required: true
        }
    },

    watch: {
        errors: {
            handler: function (errors) {
                if (errors) {
                    this.toast(
                        Object.values(errors).join('<br>'),
                    );
                }
            },
            deep: true
        },

        flash: {
            handler: function (flash) {
                if (flash) {
                    this.toast(flash.message, 4000);
                }
            },
            deep: true
        }
    },

    methods: {
        toast: function (html, title, icon, timer) {
            title = title || 'Error';
            icon = icon || 'error';
            timer = timer || 4000;
            
            this.$swal.fire({
                position: 'top-end',
                toast: true,
                icon: icon,
                title: title,
                html: html,
                showClass: { popup: 'animate__animated animate__fadeInDown' },
                hideClass: { popup: 'animate__animated animate__fadeOutUp'  },
                timer: timer,
                timerProgressBar: true,
                showConfirmButton: false,
            });
        }
    }
}
</script>