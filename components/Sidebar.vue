<template>
  <aside class="stick top-[65px] h-[calc(100vh-65px)] py-5">
    <div
      class="flex h-full w-full flex-col overflow-y-auto rounded-md border bg-card pb-5 scrollbar-thin scrollbar-thumb-input scrollbar-thumb-rounded-md"
    >
      <SidebarItem :links="menu" />

      <div class="mt-auto">
        <SidebarItem :links="bottomMenu" />
      </div>
    </div>
  </aside>
</template>

<script lang="ts" setup>
const bottomMenu = [
  {
    title: "Settings",
    icon: "heroicons:cog-6-tooth",
  },
  {
    title: "Help",
    icon: "heroicons:question-mark-circle",
  },
  {
    title: "Logout",
    icon: "heroicons:arrow-left-on-rectangle",
  },
];
const menu = [
  {
    title: "Dashboard",
    icon: "heroicons:home",
  },
  {
    title: "Customers",
    icon: "heroicons:user-group",
    items: [
      {
        title: "List",
        items: [
          { title: "List" },
          { title: "Create" },
          { title: "Edit" },
          { title: "Delete" },
          { title: "Details" },
        ],
      },
      { title: "Create" },
      { title: "Edit" },
      { title: "Delete" },
      { title: "Details" },
    ],
  },
  {
    title: "Orders",
    icon: "heroicons:shopping-cart",
    items: [
      { title: "List" },
      { title: "Create" },
      { title: "Edit" },
      { title: "Delete" },
      { title: "Details" },
    ],
  },
  {
    title: "Products",
    icon: "heroicons:cube",
    items: [
      { title: "List" },
      { title: "Create" },
      { title: "Edit" },
      { title: "Delete" },
      { title: "Details" },
    ],
  },
  {
    title: "Staff",
    icon: "heroicons:cube",
    items: [
      { title: "List" },
      { title: "Create" },
      { title: "Edit" },
      { title: "Delete" },
      { title: "Details" },
    ],
  },
  {
    title: "Analytics",
    icon: "heroicons:chart-pie-solid",
    items: [
      { title: "List" },
      { title: "Create" },
      { title: "Edit" },
      { title: "Delete" },
      { title: "Details" },
    ],
  },
];
</script>

<style></style>
