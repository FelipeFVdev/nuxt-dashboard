<template>
  <div>
    <!-- HEADER -->
    <Header />

    <div class="container lg:grid lg:grid-cols-12 lg:gap-10">
      <!-- Sidebar -->
      <Sidebar class="hidden lg:col-span-3 lg:block" />

      <!-- Main Section -->
      <main class="py-5 lg:col-span-6">
        <!-- Status Card -->
        <StatusCard />

        <!-- Customer List -->
        <NewCostumers />

        <!-- Sales Chart -->
        <SalesChart />

        <!-- Recent Orders -->
        <RecentOrders />
      </main>

      <div>
        <!-- Profile Info -->

        <!-- Reminders -->
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup></script>

<style></style>
