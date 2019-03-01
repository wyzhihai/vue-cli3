<template>
  <div class="row">
    <div class="col-2">
      <button class="btn btn-secondary button" @click="sort">
        To original order
      </button>
    </div>

    <div class="col-6">
      <h3>Transition</h3>
      <draggable
        class="list-group"
        tag="ul"
        v-model="list"
        v-bind="dragOptions"
        @start="drag = true"
        @end="drag = false"
      >
        <transition-group type="transition" :name="!drag ? 'flip-list' : null">
          <li
            class="list-group-item"
            v-for="element in list"
            :key="element.order"
          >
            <i
              :class="
                element.fixed ? 'fa fa-anchor' : 'glyphicon glyphicon-pushpin'
              "
              @click="element.fixed = !element.fixed"
              aria-hidden="true"
            ></i>
            {{ element.name }}
          </li>
        </transition-group>
      </draggable>
    </div>

   
  </div>
</template>
script
style
