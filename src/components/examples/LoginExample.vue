<script setup lang="ts">
import { ref } from 'vue';
import { Button, Card, Icon, Input } from '@/components/ui';

const username = ref('');
const password = ref('');
</script>

<template>
  <div class="wa-stack wa-justify-content-center wa-align-items-center">
    <Card style="width: 400px; margin-top: 40px">
      <div class="wa-stack wa-gap-l">
        <form class="wa-stack wa-gap-m" @submit.prevent>
          <Input v-model="username" label="Username" type="text" />
          <Input
            v-model="password"
            label="Password"
            type="password"
            password-toggle
          />

          <p v-if="username" class="wa-caption-s">
            Username: <strong>{{ username }}</strong>
          </p>
          <p v-if="password" class="wa-caption-s">
            Password: <strong>{{ '*'.repeat(password.length) }}</strong>
          </p>

          <div>
            <a href="#" class="wa-caption-s">Forgot password?</a>
          </div>

          <Button variant="brand" size="medium">Sign In</Button>
        </form>

        <div class="wa-cluster wa-justify-content-center wa-gap-2xs">
          <span class="wa-caption-s">OR</span>
        </div>

        <div class="wa-stack wa-gap-xs">
          <Button appearance="outlined" size="medium">
            <Icon slot="start" name="github" family="brands" />
            Continue with GitHub
          </Button>
        </div>

        <div
          class="wa-caption-s"
          :style="{ textAlign: 'center', color: 'var(--wa-color-neutral-60)' }"
        >
          Don't have an account? <a href="#">Sign up</a>
        </div>
      </div>
    </Card>
  </div>
</template>
