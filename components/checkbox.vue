<!--
      Copyright (C) 2019  SuperGreenLab <towelie@supergreenlab.com>
      Author: Constantin Clauzel <constantin.clauzel@gmail.com>

      This program is free software: you can redistribute it and/or modify
      it under the terms of the GNU General Public License as published by
      the Free Software Foundation, either version 3 of the License, or
      (at your option) any later version.

      This program is distributed in the hope that it will be useful,
      but WITHOUT ANY WARRANTY; without even the implied warranty of
      MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
      GNU General Public License for more details.

      You should have received a copy of the GNU General Public License
      along with this program.  If not, see <http://www.gnu.org/licenses/>.
 -->

<template>
  <section :id='$style.container' :class='label && !nomarginright ? $style.withlabel : ""'>
    <div :id='$style.border' :class='checked ? $style.selected : ""' v-on:click='click()'>
      <div :id='$style.checkboxcenter' :style='{"background-color": color}'></div>
    </div>
    {{ label }}
  </section>
</template>

<script>
export default {
  props: ['color', 'label', 'checked', 'nomarginright'],
  methods: {
    click() {
      this.$emit('click')
    },
  },
}
</script>

<style module lang=stylus>

#container
  display: flex
  align-items: center
  justify-content: center
  white-space: nowrap

.withlabel
  margin-right: 20pt

#border
  position: relative
  display: flex
  align-items: center
  justify-content: center
  width: 20pt
  height: 20pt
  margin-right: 5pt
  border: 1px solid #C4C4C4
  border-radius: 2pt
  cursor: pointer
  transition: box-shadow 0.2s

#checkboxcenter
  width: 100%
  height: 100%
  border: 2pt solid white
  border-radius: 2pt

.selected
  box-shadow: 0 0 0 2pt #3AB20B

</style>
