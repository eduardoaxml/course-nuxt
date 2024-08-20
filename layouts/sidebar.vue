<template>
    <main class="main-layout">
        <article class="sidebar">
            <p>Dashboard</p>
            <p>Settings</p>
        </article>
        <section>
            <slot></slot>
        </section>
        
    </main>
</template>

<style>
    .sidebar {
        width: 250px;
    }
    .main-layout {
        display: flex;
        gap: 10px;
        min-height: 100dvh;
        width: 100%;
    }
</style>