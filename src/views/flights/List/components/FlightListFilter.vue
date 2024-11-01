<template>
  <b-form class="rounded-3 shadow">
    <!-- Popular filters -->
    <b-card no-body class="card-body rounded-0 rounded-top p-4">
      <h6 class="mb-2">Popular Filters</h6>
      <b-col cols="12">
        <div class="d-flex justify-content-between align-items-center">
          <b-form-checkbox id="popularType1">Refundable Fare</b-form-checkbox>
          <span class="small">(41)</span>
        </div>

        <div class="d-flex justify-content-between align-items-center">
          <b-form-checkbox id="popularType2">1 Stop</b-form-checkbox>
          <span class="small">(20)</span>
        </div>

        <div class="d-flex justify-content-between align-items-center">
          <b-form-checkbox id="popularType3">Late Departure</b-form-checkbox>
          <span class="small">(4)</span>
        </div>

        <div class="d-flex justify-content-between align-items-center">
          <b-form-checkbox id="popularType4">Non-Stop</b-form-checkbox>
          <span class="small">(2)</span>
        </div>
      </b-col>
    </b-card>

    <hr class="my-0" />

    <!-- Price -->
    <b-card no-body class="card-body rounded-0 p-4">
      <h6 class="mb-2">Price</h6>
      <div class="position-relative">
        <div class="d-flex justify-content-between">
          <span>{{ currency }} {{ value[0] }}</span>
          <span>{{ currency }} {{ value[1] }}</span>
        </div>
        <VueSlider
          v-model="value"
          :min="500"
          :max="1500"
          :dotSize="19"
          :dotStyle="dotStyle"
          :processStyle="processStyle"
          :railStyle="railStyle"
          tooltip="none"
        />
      </div>
    </b-card>

    <hr class="my-0" />

    <!-- Onward stops -->
    <b-card no-body class="card-body rounded-0 p-4">
      <h6 class="mb-2">Onward Stops</h6>
      <ul class="list-inline mb-0 g-3">
        <li class="list-inline-item mb-0">
          <input type="checkbox" class="btn-check" id="btn-check-c1" />
          <label class="btn btn-sm btn-light btn-primary-soft-check" for="btn-check-c1"
            >Direct</label
          >
        </li>
        <li class="list-inline-item mb-0">
          <input type="checkbox" class="btn-check" id="btn-check-c2" />
          <label class="btn btn-sm btn-light btn-primary-soft-check" for="btn-check-c2"
            >1 Stop</label
          >
        </li>
        <li class="list-inline-item mb-0">
          <input type="checkbox" class="btn-check" id="btn-check-c3" />
          <label class="btn btn-sm btn-light btn-primary-soft-check" for="btn-check-c3"
            >2+ Stops</label
          >
        </li>
      </ul>
    </b-card>

    <hr class="my-0" />

    <!-- Return Stops -->
    <b-card no-body class="card-body rounded-0 p-4">
      <h6 class="mb-2">Return Stops</h6>
      <ul class="list-inline mb-0 g-3">
        <li class="list-inline-item mb-0">
          <input type="checkbox" class="btn-check" id="btn-check-6" />
          <label class="btn btn-sm btn-light btn-primary-soft-check" for="btn-check-6"
            >Direct</label
          >
        </li>
        <li class="list-inline-item mb-0">
          <input type="checkbox" class="btn-check" id="btn-check-7" />
          <label class="btn btn-sm btn-light btn-primary-soft-check" for="btn-check-7"
            >1 Stop</label
          >
        </li>
        <li class="list-inline-item mb-0">
          <input type="checkbox" class="btn-check" id="btn-check-8" />
          <label class="btn btn-sm btn-light btn-primary-soft-check" for="btn-check-8"
            >2+ Stops</label
          >
        </li>
      </ul>
    </b-card>

    <hr class="my-0" />

    <!-- Preferred Airline -->
    <b-card no-body class="card-body rounded-0 p-4">
      <h6 class="mb-2">Preferred Airline</h6>
      <b-col cols="12">
        <div class="form-check">
          <input class="form-check-input" type="checkbox" value="" id="airlineType1" />
          <label class="form-check-label" for="airlineType1">
            <img :src="element12" class="h-15px fa-fw me-2" alt="" />Blogzine
          </label>
        </div>

        <div class="form-check">
          <input class="form-check-input" type="checkbox" value="" id="airlineType2" />
          <label class="form-check-label" for="airlineType2">
            <img :src="element13" class="h-15px fa-fw me-2" alt="" />Wizixo
          </label>
        </div>

        <div class="form-check">
          <input class="form-check-input" type="checkbox" value="" id="airlineType3" />
          <label class="form-check-label" for="airlineType3">
            <img :src="element14" class="h-15px fa-fw me-2" alt="" />Folio airline
          </label>
        </div>

        <div class="form-check">
          <input class="form-check-input" type="checkbox" value="" id="airlineType4" />
          <label class="form-check-label" for="airlineType4">
            <img :src="element15" class="h-15px fa-fw me-2" alt="" />Booking
          </label>
        </div>

        <b-collapse class="multi-collapse" id="airlineCollapse">
          <div class="form-check">
            <input class="form-check-input" type="checkbox" value="" id="airlineType7" />
            <label class="form-check-label" for="airlineType7">
              <img :src="element15" class="h-15px fa-fw me-2" alt="" />Formex
            </label>
          </div>

          <div class="form-check">
            <input class="form-check-input" type="checkbox" value="" id="airlineType8" />
            <label class="form-check-label" for="airlineType8">
              <img :src="element13" class="h-15px fa-fw me-2" alt="" />Realty
            </label>
          </div>

          <div class="form-check">
            <input class="form-check-input" type="checkbox" value="" id="airlineType9" />
            <label class="form-check-label" for="airlineType9">
              <img :src="element12" class="h-15px fa-fw me-2" alt="" />rocyon
            </label>
          </div>
        </b-collapse>

        <a
          v-b-toggle.airlineCollapse
          class="p-0 mb-to mt-2 btn-more d-flex align-items-center collapsed"
          data-bs-toggle="collapse"
          href="#airlineCollapes"
          role="button"
          aria-expanded="false"
          aria-controls="airlineCollapes"
        >
          See <span class="see-more ms-1">more</span><span class="see-less ms-1">less</span>
          <font-awesome-icon :icon="faAngleDown" class="ms-2" />
        </a>
      </b-col>
    </b-card>

    <hr class="my-0" />

    <!-- Layover Airport -->
    <b-card no-body class="card-body rounded-0 rounded-bottom p-4">
      <h6 class="mb-2">Layover Airport</h6>
      <b-col cols="12">
        <div class="d-flex justify-content-between align-items-center">
          <b-form-checkbox id="layoverType1">Abu Dhabi</b-form-checkbox>
          <span class="small">(01)</span>
        </div>

        <div class="d-flex justify-content-between align-items-center">
          <b-form-checkbox id="layoverType2">Amsterdam</b-form-checkbox>
          <span class="small">(02)</span>
        </div>

        <div class="d-flex justify-content-between align-items-center">
          <b-form-checkbox id="layoverType3">Chicago</b-form-checkbox>
          <span class="small">(02)</span>
        </div>

        <div class="d-flex justify-content-between align-items-center">
          <b-form-checkbox id="layoverType4">Doha</b-form-checkbox>
          <span class="small">(03)</span>
        </div>

        <b-collapse class="multi-collapse" id="lauoverCollapse">
          <div class="d-flex justify-content-between align-items-center">
            <b-form-checkbox id="layoverType5">Dubai</b-form-checkbox>
            <span class="small">(04)</span>
          </div>

          <div class="d-flex justify-content-between align-items-center">
            <b-form-checkbox id="layoverType6">New Delhi</b-form-checkbox>
            <span class="small">(15)</span>
          </div>

          <div class="d-flex justify-content-between align-items-center">
            <b-form-checkbox id="layoverType6">Paris</b-form-checkbox>
            <span class="small">(04)</span>
          </div>
        </b-collapse>

        <a
          class="btn-more d-flex align-items-center collapsed p-0 mb-0 mt-2"
          v-b-toggle.lauoverCollapse
          href="#lauoverCollapes"
          role="button"
          aria-expanded="false"
          aria-controls="lauoverCollapes"
        >
          See <span class="see-more ms-1">more</span><span class="see-less ms-1">less</span>
          <font-awesome-icon :icon="faAngleDown" class="me-2" />
        </a>
      </b-col>
    </b-card>
  </b-form>

  <div class="d-flex justify-content-between p-2 p-xl-0 mt-xl-4">
    <b-button variant="link" class="p-0 mb-0">Clear all</b-button>
    <b-button variant="primary" class="mb-0">Filter Result</b-button>
  </div>
</template>

<script lang="ts" setup>
import element12 from '@/assets/images/element/12.svg'
import element13 from '@/assets/images/element/13.svg'
import element14 from '@/assets/images/element/14.svg'
import element15 from '@/assets/images/element/15.svg'

import { faAngleDown } from '@fortawesome/free-solid-svg-icons'
import { ref } from 'vue'
import VueSlider from 'vue-3-slider-component'
import { currency } from '@/helpers/constants'

const value = ref([700, 1000])

const dotStyle = {
  backgroundColor: '#5143d9',
  border: '5px solid #fff',
  boxShadow: '0px 0px 0px 1px #5143d9'
}

const processStyle = {
  backgroundColor: '#5143d9'
}

const railStyle = {
  backgroundColor: 'rgb(81, 67, 217, 0.1)'
}
</script>
