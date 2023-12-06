<script>
export default {
    data() {
        return {
            restaurant: {
                id: "restaurant",
                title: "FIND OUR RESTAURANTS",
                element: [
                    {
                        street: "1614 E. Bell Rd #104",
                        city: "Salerno, AZ 85022",
                        telephone: "(602) 867-1010"
                    },

                    {
                        street: "204 E Pizzetta Tommaso",
                        city: "Sorrento, AZ 85022",
                        telephone: "(358) 867-1010"
                    },

                    {
                        street: "Viale Puglia 54",
                        city: "Torre Del Greco AZ 85022",
                        telephone: "(359) 867-1010"
                    },


                    {
                        street: "Corso Itali AA",
                        city: "Naples, AZ 85022",
                        telephone: "(989) 867-1010"
                    },


                ]
            },
            workingHours: {
                id: "workingHours",
                title: "WORKING HOURS",
                element: [
                    {
                        dayWork: "MONDAY",
                        hoursWork: " Kitchen Closed"
                    },
                    {
                        dayWork: "TUSEDAT UNITL FRIDAY",
                        hoursWork: " 9:00 - 22:00"
                    },
                    {
                        dayWork: "SATURDAY",
                        hoursWork: " Saturdy 11am to midnight"
                    },
                    {
                        dayWork: "SUNDAY",
                        hoursWork: " 9:00 - 22:00"
                    },

                ],
            },
        }
    },
}
</script>

<template>
    <div class="row footer">
        <!-- IMG -->
        <div class="col">
            <img class="img" src="../assets/img/footer-img-1.jpg" alt="">
        </div>

        <!-- card -->
        <div class="col-list">
            <ul>
                <li>
                    <div class="restaurant-title">{{ restaurant.title }}</div>
                </li>

                <li class="restaurant" v-for="(element, index) in restaurant.element">
                    <div class="street"> {{ element.street }} </div>
                    <div class="city"> {{ element.city }} </div>
                    <div class="teleph"> {{ element.telephone }}</div>
                </li>
            </ul>

            <ul>
                <li>
                    <div class="workingHours-title"> {{ workingHours.title }}</div>
                </li>

                <li class="workingHours" v-for="(element, index) in workingHours.element">
                    <div class="day-work">{{ element.dayWork }}</div>
                    <div class="hours-work" :class="`hours-work-${index}`"> {{ element.hoursWork }} </div>
                </li>
            </ul>

            <p>THE DON PEPPE CREW FIRST AND FOREMOST VALUES BAKED SLICE OF PIZZA.</p>
            <img src="" alt="">
        </div>

        
    </div>
</template>

<style  scoped lang="scss">
@use '../style/partials/mixin' as*;
@use '../style/partials/variables' as*;

.row {
    @include flex (row, space-between, stretch);
    flex-direction: row-reverse;


    .col,
    .col-list {
        width: 50%;
        background-color: $bg-Nav-Bar;
    }

    .col-list {
        @include flex(row, space-between, start);

        p, ul {
            width: calc(100% / 3);
            margin-top: 30px;
        }

        .restaurant-title,
        .workingHours-title {
            font-weight: 600;
            font-size: .8rem;
            color: $color-text-title-footer;
            margin-bottom: 15px;
        }

        .restaurant,
        .workingHours {
            margin: 10px 0;
            font-size: .7rem;
            color: $color-text-element-footer;

            .day-work {
                color: $color-text-day-work-footer;
            }

            .hours-work-0 {
                color: $color-text-hours-work-footer;
            }
        }

        p {
            color: white;
            font-size: .8rem;
            font-weight: 600;
        }

    }
}
</style>