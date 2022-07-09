---
title: "week2_basic"
author: "Aaron"
date: "9/7/2022"
output: html_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

## App
```{r}
    library(leaflet)
    my_map <- leaflet() %>%
        addTiles()
```

## Let's add some markers
```{r}
    my_map <- my_map %>%
        addMarkers(lat=3.194220, lng=101.736800, popup="Example")
        my_map
```

## More markers
```{r}
    set.seed(42)
    df <- data.frame(lat = runif(20, min = 39.2, max=39.3), lng=runif(20,min=-76.6, max=-76.5))
    df %>%
        leaflet() %>%
        addTiles() %>%
        addMarkers()
```

## Custom Markers
```{r}
    university_lat_long <- data.frame(lat=c(39.2973166,39.3288851, 39.2906617, 39.2970681, 39.2824806),
                                      lng=c(-76.5929798, -76.6206598,-76.5479783, -76.6150537, -76.6016766))
    university_lat_long %>%
        leaflet() %>%
        addTiles() %>%
        addMarkers()
```

## Multiple PopUps
```{r}
    sites <- c(
        "<a hrf='http://www.jhsph.edu/'>East Campus</a>",
        "<a href='https://apply.jhu.edu/visit/homewood/'>Homewood Campus</a>",
        "<a href='http://www.hopkinsmedicine.org/john_hopkins_bayview/'>Bayview Medical Center</a>",
        "<a href='http://peabody.jhu.edu/'>Peabody Institute</a>",
        "< href='http://carey.jhu.edu/'>Carey Business School</a>"
    )

    university_lat_long %>%
        leaflet() %>%
        addTiles() %>%
        addMarkers(popup=sites)
```
