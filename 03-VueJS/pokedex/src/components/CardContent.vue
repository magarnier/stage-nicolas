<!--
  - Copyright (c) Enalean, 2020 - present. All Rights Reserved.
  -
  -  This file is a part of Tuleap.
  -
  - Tuleap is free software; you can redistribute it and/or modify
  - it under the terms of the GNU General Public License as published by
  - the Free Software Foundation; either version 2 of the License, or
  - (at your option) any later version.
  -
  - Tuleap is distributed in the hope that it will be useful,
  - but WITHOUT ANY WARRANTY; without even the implied warranty of
  - MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
  - GNU General Public License for more details.
  -
  - You should have received a copy of the GNU General Public License
  - along with Tuleap. If not, see <http://www.gnu.org/licenses/>.
  -
  -->

<template>
    <div>
        <div class="pokemon-card-info">
            <a v-bind:href="getUrl">{{pokemon.id}}</a>
            {{pokemon.name}}
        </div>
        <img
            v-bind:alt="getTitle"
            class="pokemon-image"
            v-if="pokemon.id <= 6"
            v-bind:src="require(`../assets/${pokemon.id}.jpg`)"
        /><img
            v-bind:alt="getTitle"
            class="pokemon-image"
            v-else
            v-bind:src="require(`../assets/pokeball.jpg`)"
        />
    </div>
</template>

<script>
    export default {
        name: "CardContent",
        props: {
            pokemon: Object
        },
        computed: {
            getUrl() {
                return "https://www.pokepedia.fr/" + this.pokemon.name;
            },

            getTitle() {
                return this.pokemon.id + " - " + this.pokemon.name;
            }
        }
    };
</script>

<style scoped>

    .pokemon-card-info {
        margin: 10px 0 0 10px;
        width: 100%;
    }

    .pokemon-image {
        max-width: 40px;
        margin: 10px 20px;
    }
</style>