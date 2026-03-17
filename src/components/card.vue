<script>
export default {
  props: ['item']
}
</script>

<template>
    <div class="card">
        <div class="extension_info">
            <img :src="item.logo" :alt="item.name + ' icon'">
            <div class="extension_details">
                <h2 class="text_preset_2">{{ item.name }}</h2>
                <p class="text_preset_5">{{ item.description }}</p>
            </div>
        </div>
        <div class="extension_actions">
            <button class="text_preset_6">Remove</button>
            <div class="toggle_button">
                <div class="circle"></div>
            </div>
        </div>
    </div>
</template>