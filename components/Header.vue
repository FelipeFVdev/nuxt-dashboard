<template>
  <header class="sticky top-0 z-20 border-b bg-background/80 backdrop-blur">
    <!-- Flex Container -->
    <div class="container flex h-16 items-center justify-between">
      <!-- Logo page image -->
      <div class="flex items-center gap-3">
        <!-- logo -->
        <img
          src="/icon.svg"
          alt="Analytics Logo"
          class="h-7 w-7 object-contain"
        />
        <!-- Page Title -->
        <NuxtLink class="text-xl font-bold" to="/">Analytics</NuxtLink>
      </div>

      <!-- Right side of the header -->
      <div class="flex items-center gap-5">
        <button
          @click="toggleTheme"
          aria-label="Toggle Theme"
          class="flex h-9 w-9 shrink-0 items-center justify-center rounded-full border bg-background"
        >
          <Icon name="heroicons:sun" class="h-5 w-5" />
        </button>
        <!-- Profile dropdown menu -->
        <HMenu as="div" class="relative">
          <HMenuButton
            class="flex h-9 w-9 shrink-0 items-center justify-center overflow-hidden rounded-full border bg-background"
          >
            <img
              src="https://randomuser.me/api/portraits/med/men/75.jpg"
              alt="Logged in user"
              class="w-full h-full"
            />
          </HMenuButton>

          <TransitionScale :scale="0.8" origin="top right">
            <HMenuItems
              class="absolute right-0 z-10 mt-3 w-48 rounded-md border bg-background focus:outline-none focus-visible:ring-2 focus-visible:ring-ring"
            >
              <div class="border-b px-3 py-1.5 text-sm">
                <p class="font-semibold">Hello John</p>
                <a
                  href="mailto:johndoe@test.com"
                  class="leading-none text-muted-foreground"
                  >johndoe@test.com</a
                >
              </div>

              <div class="p-1">
                <template v-for="(p, i) in profileMenuOptions" :key="i" as="">
                  <HMenuItem v-if="!p.divider" v-slot="{ active }" class="">
                    <button
                      @click="p.click?.()"
                      :class="[active && 'bg-muted']"
                      class="inline-flex w-full items-center rounded-md p-2 text-sm font-medium"
                    >
                      {{ p.title }}
                    </button>
                  </HMenuItem>
                  <hr v-if="p.divider" class="my-1" />
                </template>
              </div>
            </HMenuItems>
          </TransitionScale>
        </HMenu>
      </div>
    </div>
  </header>
</template>

<script lang="ts" setup>
const mode = useColorMode();
const toggleTheme = () => {
  mode.value = mode.value === "light" ? "dark" : "light";
};

const profileMenuOptions = [
  { title: "Profile" },
  { title: "Billing" },
  { title: "Settings" },
  { tittle: "Team members" },
  { title: "Sales" },
  { divider: true },
  { title: "Logout", click: () => alert("Logout") },
];
</script>

<style></style>
