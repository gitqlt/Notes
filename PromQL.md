Prometheus Query Language (w. Grafana expresssion)
====
**Arithmetic operation safe**

    scrape_duration_seconds + on(device) group_left() avg(android_device_name) by (device)
 * `group_left:`            Left side is fine, but right side has extra labels? Use group_left()!
 * `group_left:`            group_left() does NOT "group" values— it just keeps??? extra labels on the right
 * `on():`                  on() selects which labels must match. group_left() allows extra ones to stay  

**Muliply by 1, but add extra label (from right)**

    avg(android_scrape_duration_seconds)without(_dummy) * on(instance) group_left(secureBT)android_device_name
      Same:
    avg(android_scrape_duration_seconds)without(_dummy) * on(instance) group_left(secureBT)android_device_name{}
      Grafana:
    avg(android_scrape_duration_seconds)without(_dummy) * on(instance) group_left(secureBT)android_device_name{secureBT=~"$gBT"}
