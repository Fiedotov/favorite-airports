<template></template>
<script>
import airports from '~/data/airports.js'

export default {
    name: 'AirportDetailPage',
    asyncData(context) {
        const airport = airports.filter(airport => airport.abbreviation === context.route.params.code.toUpperCase())[0]
        return {
            airport
        }
    },
    head() {
        return {
            title: 'Airport Information | Aiport App',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'Detailed information about the specific airport.'
                }
            ]
        }
    },
    layout: 'AirportDetail'
}
</script>