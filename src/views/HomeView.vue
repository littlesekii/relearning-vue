<script setup>
import DirectiveConditional from '@/components/Directives/DirectiveConditional.vue';
import DirectiveVBind from '@/components/Directives/DirectiveVBind.vue';
import DirectiveVFor from '@/components/Directives/DirectiveVFor.vue';
import LifecycleHooks from '@/components/LifecycleHooks.vue';
import Reactivity from '@/components/Reactivity.vue';
import DirectiveEvents from '@/components/Directives/DirectiveEvents.vue';
import DirectiveVModel from '@/components/Directives/DirectiveVModel.vue';
import EventModifiers from '@/components/EventModifiers.vue';
import ComputedProperties from '@/components/ComputedProperties.vue';
import ComponentProps from '@/components/ComponentProps.vue';
import EmitParent from '@/components/Emit/EmitParent.vue';
import BasicSlot from '@/components/Slot/BasicSlot.vue';
import ScopedSlotParent from '@/components/Slot/ScopedSlotParent.vue';
</script>

<template>
  <!-- <LifecycleHooks /> -->
  <!-- <Reactivity /> -->
  <!-- <DirectiveVFor /> -->
  <!-- <DirectiveConditional /> -->
  <!-- <DirectiveVBind /> -->
  <!-- <DirectiveEvents /> -->
  <!-- <DirectiveVModel /> -->
  <!-- <EventModifiers /> -->
  <!-- <ComputedProperties /> -->
  <!-- <ComponentProps name="Davi" age="22" /> -->
  <!-- <EmitParent /> -->
  <!-- <BasicSlot>
    <template v-slot:header>
      Header
    </template>

    <!-- This template tag can be ommited because its the default ->
    <template v-slot:default>
      default content
    </template>
    
    <template #footer>
      Footer
    </template>
  </BasicSlot> -->

  <ScopedSlotParent />

</template>
