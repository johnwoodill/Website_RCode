        borders = geom_polygon(data=map_base_data,                         # Draws boundaries
                               map_base_aesthetics,
                               color="black", fill=NA)

        ggplot(data=inside_points, aes(x=longitude, y=latitude))  +      # Setup ggplot2
          geom_tile(aes(fill=APPT)) +                                    # Initial overlay of appt
          stat_contour(aes(z=APPT)) +                                    # Create contours for concentrations
          coord_equal() +                                                # Equalize plots
          scale_fill_gradient2(low="blue", mid="white",high="darkgreen", # Set colors for low, mid, high
                               midpoint=mean(inside_points$APPT)) +
          ggtitle("California Precipitation - 2000") +                  # Plot title
          borders                                                       # Draw California border


image: ![California-2000](/images/California_appt.png)

#### References

Thanks to @kdauria on Stack Exchange for helping with the code for interpolation and countour plots.

[CRAN Task View: Analysis of Spatial Data](http://cran.r-project.org/web/views/Spatial.html)

[Introduction to Visualising Spatial Data in R](http://cran.r-project.org/doc/contrib/intro-spatial-rl.pdf)

[The R Book - Michael J. Crawley](http://www.amazon.com/R-Book-Michael-J-Crawley/dp/0470973927/ref=sr_1_1?ie=UTF8&qid=1422422058&sr=8-1&keywords=The+R+Book&pebp=1422422059942&peasin=470973927)

[ggplot2 Help Topics](http://docs.ggplot2.org/current/)

**Examples**

[Mapping Seattle Crime](http://www.sharpsightlabs.com/mapping-seattle-crime/)

[Mapping San Francisco Crime](http://www.sharpsightlabs.com/mapping-san-francisco-crime/)

[this is how i did it...mapping in r with ggplot2](http://nrelscience.org/2013/05/30/this-is-how-i-did-it-mapping-in-r-with-ggplot2

