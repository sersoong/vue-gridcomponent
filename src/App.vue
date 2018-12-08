<template>
    <div id="demo">
        <form id="search">
            Search <input name="query" v-model="searchQuery" >
        </form>
        <demogrid
        :data='gridData'
        :columns='gridColumns'
        :filter-key='searchQuery'
        >
        </demogrid>
    </div>
</template>

<script>
import demogrid from './components/DemoGrid'
export default {
    name: 'App',
    data () {
        return {
            searchQuery: '',
            gridColumns: ['name', 'power', 'test'],
            gridData: [
                {name: 'Chuck Norris', power: Infinity, test: 'func'},
                {name: 'Bruce Lee', power: 9000, test: 'dev'},
                {name: 'Jackie chan', power: 7000, test: 'eve'},
                {name: 'Jet Li', power: 8000, test: 'ada'}
            ]
        }
    },
    components: {
        demogrid
    }
}
</script>

<style>
body {
  font-family: Helvetica Neue, Arial, sans-serif;
  font-size: 14px;
  color: #444;
}

table {
  border: 2px solid #42b983;
  border-radius: 3px;
  background-color: #fff;
}

th {
  background-color: #42b983;
  color: rgba(255,255,255,0.66);
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

td {
  background-color: #f9f9f9;
}

th, td {
  min-width: 120px;
  padding: 10px 20px;
}

th.active {
  color: #fff;
}

th.active .arrow {
  opacity: 1;
}

.arrow {
  display: inline-block;
  vertical-align: middle;
  width: 0;
  height: 0;
  margin-left: 5px;
  opacity: 0.66;
}

.arrow.asc {
  border-left: 4px solid transparent;
  border-right: 4px solid transparent;
  border-bottom: 4px solid #fff;
}

.arrow.dsc {
  border-left: 4px solid transparent;
  border-right: 4px solid transparent;
  border-top: 4px solid #fff;
}
</style>
