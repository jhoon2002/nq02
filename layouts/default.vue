<script setup>
const isOpen = ref(true)
</script>
<template>
    <!--
1. Apply h-screen at flex flex-col layout
2. Apply overflow-y-hidden at main container
3. Apply overflow-y-auto to column that needs scroll
 -->
    <div class="min-h-screen flex flex-col h-screen">
        <header class="h-20 p-2 flex items-center gap-3 border-b">
            <div class="text-xl">연극원 입시 관리 시스템</div>
            <button @click="isOpen = !isOpen">펼침 메뉴</button>
        </header>
        <!-- main container -->
        <div class="flex-1 flex flex-row overflow-y-hidden">
            <nav
                class="order-1overflow-y-auto h-screen duration-200 border-r relative w-60"
                :style="{ left: isOpen ? '0' : '-200px' }"
            >
                <div class="transition-opacity ease-in duration-75 p-2" :class="isOpen ? 'opacity-100' : 'opacity-0'">
                    사이드 메뉴
                </div>
            </nav>
            <div class="order-2 flex flex-col overflow-y-auto container mx-auto">
                <main class="h-screen p-2">
                    내용<br /><br />
                    내용<br /><br />
                    내용<br /><br />
                </main>
                <footer class="h-20 p-2 text-sm flex items-center gap-2 border-t">
                    <div>한국예술종합학교 연극원 신입생 선발시험</div>
                    <div>Drama School Admissions,</div>
                    <div>Korea National University of Arts</div>
                </footer>
            </div>
        </div>
        <!-- end main container -->
    </div>
</template>
