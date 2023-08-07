<template>
    <div class="tree-template-control-wrapper">
        <ejs-treeview id="template" :fields="fields" :nodeTemplate="'nodeTemplate'"
                                    cssClass="custom">
          <template v-slot:nodeTemplate="{data}">
            <div v-if="data.image">
              <img class='image' :src='data.image' alt='employee'/>
            </div>
            <span>{{ data.name }}</span>
            <div v-if="data.count" class="nodeBadge">
            <span class="e-badge e-badge-primary">{{ data.count }}</span>
          </div>
          </template>
        </ejs-treeview>
    </div>
</template>

<script setup>
import { TreeViewComponent as EjsTreeview } from "@syncfusion/ej2-vue-navigations";
const data =  [
        { "id": 1, "name": "Favorites", "hasChild": true},
        { "id": 2,"pid": 1, "name": "Sales Reports", icon:"pdf" },
        { "id": 4,"pid": 1, "name": "Marketing Reports", icon:"pdf"},
        { "id": 3,"pid": 1, "name": "Pictures", "hasChild": true},
        { "id": 13,"pid": 3, "name": "Employee1", image: "https://ej2.syncfusion.com/demos/src/treeview/images/employees/1.png"},
        { "id": 14,"pid": 3, "name": "Employee2", image: "https://ej2.syncfusion.com/demos/src/treeview/images/employees/2.png"},
        { "id": 5, "name": "My Folder", "hasChild": true, "expanded": true },
        { "id": 6,"pid": 5, "name": "Inbox",  "selected": true, "count":51 },
        { "id": 7,"pid": 5,  "name": "Drafts", "count":9},
        { "id": 8,"pid": 5,  "name": "Deleted Items"},
        { "id": 9,"pid": 5, "name": "Sent Items", "count":20},
        { "id": 10,"pid": 5, "name": "Sales Reports" },
        { "id": 11,"pid": 5, "name": "Marketing Reports"},
        { "id": 12,"pid": 5, "name": "Outbox"}
];
 const fields = { dataSource: data, id: 'id', parentID: 'pid', text: 'name', hasChildren: 'hasChild',
                                    iconCss:'icon'  };</script>

<style>
@import "../node_modules/@syncfusion/ej2-base/styles/material.css";
@import "../node_modules/@syncfusion/ej2-vue-navigations/styles/material.css";
@import "../node_modules/@syncfusion/ej2-inputs/styles/material.css";
@import "../node_modules/@syncfusion/ej2-buttons/styles/material.css";
@import "../node_modules/@syncfusion/ej2-vue-notifications/styles/material.css";
</style>