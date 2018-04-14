<template>
    <div class="sidenav-container">
        <div class="sidenav-backdrop" @click="$emit('close')"></div>
        <transition name="slide-side">
            <div class="sidenav">
                <ul class="nav-list" @click="emit('close')">
                </ul>
        </transition>
    </div>
</template>