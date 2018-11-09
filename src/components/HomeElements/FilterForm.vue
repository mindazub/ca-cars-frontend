<template>
    <div id="mainSearchForm">
        <div class="card">
            <div class="card-body">
                <h5 class="card-title">Car search</h5>
                <div class="row">
                    <div class="col-lg-4">
                        <div class="form-group">
                            <label for="exampleFormControlSelect1">Brand</label>
                            <select class="form-control" id="exampleFormControlSelect1">
                                <option selected value="" disabled>-Select brand-</option>
                                <option>2</option>
                                <option>3</option>
                                <option>4</option>
                                <option>5</option>
                            </select>
                        </div>
                    </div>
                    <div class="col">

                    </div>
                </div>

                <a href="#" class="btn btn-primary">Filter</a>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        props:['filterData'], // filters
        name: 'FilterForm',
        data(){
            return {
            }
        },
        methods: {
        }
    }
</script>