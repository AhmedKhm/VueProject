<template>
    <div>
        <div class="navBar">
            <b-button v-b-toggle.sidebar-1><b-icon-list></b-icon-list></b-button>
        </div>
        <b-sidebar id="sidebar-1" title="Menu" shadow width="15%">
        <div class="px-1 py-2">
          <p>
            Cras mattis consectetur purus sit amet fermentum. Cras justo odio,
            dapibus ac facilisis in, egestas eget quam. Morbi leo risus, porta
            ac consectetur ac, vestibulum at eros.
          </p>
          <br /><br /><br />
          <b-button variant="outline-danger" class="mb-2">
            <nuxt-link to="/">
              <b-icon icon="power" aria-hidden="true"></b-icon>Se
              déconnecter</nuxt-link
            >
          </b-button>
        </div>
      </b-sidebar>
      <div class="section">
                            <b-container fluid>
                    <!-- User Interface controls -->
                    <b-row>
                    <b-col lg="6" class="my-1">
                        <b-form-group
                        label="Sort"
                        label-cols-sm="3"
                        label-align-sm="right"
                        label-size="sm"
                        label-for="sortBySelect"
                        class="mb-0"
                        >
                        <b-input-group size="sm">
                            <b-form-select v-model="sortBy" id="sortBySelect" :options="sortOptions" class="w-75">
                            <template v-slot:first>
                                <option value="">-- none --</option>
                            </template>
                            </b-form-select>
                            <b-form-select v-model="sortDesc" size="sm" :disabled="!sortBy" class="w-25">
                            <option :value="false">Asc</option>
                            <option :value="true">Desc</option>
                            </b-form-select>
                        </b-input-group>
                        </b-form-group>
                    </b-col>

                    <b-col lg="6" class="my-1">
                        <b-form-group
                        label="Initial sort"
                        label-cols-sm="3"
                        label-align-sm="right"
                        label-size="sm"
                        label-for="initialSortSelect"
                        class="mb-0"
                        >
                        <b-form-select
                            v-model="sortDirection"
                            id="initialSortSelect"
                            size="sm"
                            :options="['asc', 'desc', 'last']"
                        ></b-form-select>
                        </b-form-group>
                    </b-col>

                    <b-col lg="6" class="my-1">
                        <b-form-group
                        label="Filter"
                        label-cols-sm="3"
                        label-align-sm="right"
                        label-size="sm"
                        label-for="filterInput"
                        class="mb-0"
                        >
                        <b-input-group size="sm">
                            <b-form-input
                            v-model="filter"
                            type="search"
                            id="filterInput"
                            placeholder="Type to Search"
                            ></b-form-input>
                            <b-input-group-append>
                            <b-button :disabled="!filter" @click="filter = ''">Clear</b-button>
                            </b-input-group-append>
                        </b-input-group>
                        </b-form-group>
                    </b-col>

                  

                    <b-col sm="5" md="6" class="my-1">
                        <b-form-group
                        label="Per page"
                        label-cols-sm="6"
                        label-cols-md="4"
                        label-cols-lg="3"
                        label-align-sm="right"
                        label-size="sm"
                        label-for="perPageSelect"
                        class="mb-0"
                        >
                        <b-form-select
                            v-model="perPage"
                            id="perPageSelect"
                            size="sm"
                            :options="pageOptions"
                        ></b-form-select>
                        </b-form-group>
                    </b-col>

                    <b-col sm="7" md="6" class="my-1">
                        <b-pagination
                        v-model="currentPage"
                        :total-rows="totalRows"
                        :per-page="perPage"
                        align="fill"
                        size="sm"
                        class="my-0"
                        ></b-pagination>
                    </b-col>
                    </b-row>

                    <!-- Main table element -->
                    <b-table
                    show-empty
                    small
                    stacked="md"
                    :items="items"
                    :fields="fields"
                    :current-page="currentPage"
                    :per-page="perPage"
                    :filter="filter"
                    :filter-included-fields="filterOn"
                    :sort-by.sync="sortBy"
                    :sort-desc.sync="sortDesc"
                    :sort-direction="sortDirection"
                    @filtered="onFiltered"
                    >
                    <template v-slot:cell(name)="row">
                        {{ row.value.first }} {{ row.value.last }}
                    </template>

                    <template v-slot:cell(actions)="row">
                        <b-button size="sm" @click="info(row.item, row.index, $event.target)" class="mr-1">
                        Info modal
                        </b-button>
                        <b-button size="sm" @click="row.toggleDetails">
                        {{ row.detailsShowing ? 'Hide' : 'Show' }} Details
                        </b-button>
                    </template>

                    <template v-slot:row-details="row">
                        <b-card>
                        <ul>
                            <li v-for="(value, key) in row.item" :key="key">{{ key }}: {{ value }}</li>
                        </ul>
                        </b-card>
                    </template>
                    </b-table>

                    <!-- Info modal -->
                    <b-modal :id="infoModal.id" :title="infoModal.title" ok-only @hide="resetInfoModal">
                    <pre>{{ infoModal.content }}</pre>
                    </b-modal>
                </b-container>

      </div>
    </div>
</template>

<script>
     export default {
        name:"EspaceRecruteur",
    // }
      data() {
      return {
        items: [
          { isActive: true, Diplome: 'certificat1', name: { first: 'Dickerson', last: 'Macdonald' } },
          { isActive: false, Diplome: 'certificat2', name: { first: 'Larsen', last: 'Shaw' } },
          {
            isActive: false,
            Diplome: 'certificat3',
            name: { first: 'Mini', last: 'Navarro' },
            _rowVariant: 'success'
          },
          { isActive: false, Diplome: 'certificat4', name: { first: 'Geneva', last: 'Wilson' } },
          { isActive: true, Diplome: 'certificat5', name: { first: 'Jami', last: 'Carney' } },
          { isActive: false, Diplome: 'certificat6', name: { first: 'Essie', last: 'Dunlap' } },
          { isActive: true, Diplome: 'certificat7', name: { first: 'Thor', last: 'Macdonald' } },
          {
            isActive: true,
            Diplome: 'certificat8',
            name: { first: 'Larsen', last: 'Shaw' },
            _cellVariants: { Diplome: 'danger', isActive: 'warning' }
          },
          { isActive: false, Diplome: 'certificat9', name: { first: 'Mitzi', last: 'Navarro' } },
          { isActive: false, Diplome: 'certificat10', name: { first: 'Genevieve', last: 'Wilson' } },
          { isActive: true, Diplome: 'certificat11', name: { first: 'John', last: 'Carney' } },
          { isActive: false, Diplome: 'certificat12', name: { first: 'Dick', last: 'Dunlap' } }
        ],
        fields: [
          { key: 'name', label: 'Nom et prenom', sortable: true, sortDirection: 'desc' },
          { key: 'Diplome', label: 'Diplome', sortable: true, class: 'text-center' },
          
          { key: 'actions', label: 'Actions' }
        ],
        totalRows: 1,
        currentPage: 1,
        perPage: 5,
        pageOptions: [5, 10, 15],
        sortBy: '',
        sortDesc: false,
        sortDirection: 'asc',
        filter: null,
        filterOn: [],
        infoModal: {
          id: 'info-modal',
          title: '',
          content: ''
        }
      }
    },
    computed: {
      sortOptions() {
        // Create an options list from our fields
        return this.fields
          .filter(f => f.sortable)
          .map(f => {
            return { text: f.label, value: f.key }
          })
      }
    },
    mounted() {
      // Set the initial number of items
      this.totalRows = this.items.length
    },
    methods: {
      info(item, index, button) {
        this.infoModal.title = `Row index: ${index}`
        this.infoModal.content = JSON.stringify(item, null, 2)
        this.$root.$emit('bv::show::modal', this.infoModal.id, button)
      },
      resetInfoModal() {
        this.infoModal.title = ''
        this.infoModal.content = ''
      },
      onFiltered(filteredItems) {
        // Trigger pagination to update the number of buttons/pages due to filtering
        this.totalRows = filteredItems.length
        this.currentPage = 1
      }
    }
  }
</script>

<style lang="scss" scoped>
.navBar {
  background-color: rgb(237, 241, 241);
  width: 100%;
  height: 6vh;
}
.section {
  background-color: rgb(237, 241, 241);
  width: 70%;
  height: 32rem;
  margin: 3rem 0rem 0rem 15rem;
  border-radius: 1rem;
  display: flex;
}
</style>