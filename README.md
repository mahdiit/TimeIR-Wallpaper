# TimeIR-Wallpaper
Simple Javascript code view Time.ir TV Wallpaper
![Untitled](https://user-images.githubusercontent.com/67848/182289080-840fdcab-9ce9-4711-9bb3-018bee26e380.jpg)

نمایش تقویم برای تی وی و والپیپر
بصورت لایو


```javascript
$.get('https://www.time.ir/', function (data) {
                var htmlText = $(data).find('.today-shamsi').html();
                $('#today-shamsi').html(htmlText);
                //today-gregorian
                htmlText = $(data).find('.today-gregorian').html();
                $('#today-gregorian').html(htmlText);
                //today-hijri
                htmlText = $(data).find('.today-hijri').html();
                $('#today-hijri').html(htmlText);
                //today-astrological
                htmlText = $(data).find('.today-astrological').html();
                $('#today-astrological').html(htmlText);

                $(data).find('.eventsCurrentMonthWrapper ul li').each(function (i, el) {
                    var eventHoliday = $(el).hasClass('eventHoliday');
                    if (eventHoliday) {
                        $('#marquee_data').append('<td class="red-day">' + el.innerHTML + '</td>');
                    }
                    else {
                        $('#marquee_data').append('<td>' + el.innerHTML + '</td>');
                    }
                });

                $('#cal').html($(data).find('.mainCalendar').html());
            });
```
