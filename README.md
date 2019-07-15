# daterangepicker with extended feature
Default daterangepicker plugin with some extended feature that daterangepicker not support

I was working on a project where i need to use daterangepicker and i need something like invalid dates which should come from an url.
But it seems like i didn't found any answer on stackoverflow or even in ther github repo.
So here is my extended version.


# USES

```javascript

    let url="http://example.com/json_invalid_date";
    var filter = '';
    $(document).ready(function() {
        $('.invalid_date_depend_data').on('change', '.room_list, .property_list',function(){
            filter = [{filter:'pass extra data'}];
            
            $('.date_rangepicker').daterangepicker({
                locale: {
                    separator: ' to ',
                    format: 'YYYY-MM-DD'
                },
                readOnly: true,
                invalidDatesUrl: url,
                invalidDatesFilter: filter,
            }, function(start, end, label) {
                var now = moment(start.format('YYYY-MM-DD')); //todays date
                var end = moment(end.format('YYYY-MM-DD')); // another date                
            });

        });
    });
```

## Extended Features
 1. readOnly: true/false  [this will male the input readonly when initialized]
 2. invalidDatesUrl: url [you can pass an url from where the date can be fetched by the plugin]
 
 you have to make surre that you pass the date in same format you configured the plugin
