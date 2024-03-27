# Creating a data frame
> veri <- data.frame( 
+     Ad = c("Ahmet", "Ayşe", "Mehmet", "Fatma"),
+     Yas = c(25, 30, 35, 40),
+     Maas = c(4000, 4500, 5000, 5500)
+ )
> print(veri)
      Ad Yas Maas
1  Ahmet  25 4000
2   Ayşe  30 4500
3 Mehmet  35 5000
4  Fatma  40 5500
> summary(veri)  # View the summary of the data frame
      Ad                 Yas             Maas     
 Length:4           Min.   :25.00   Min.   :4000  
 Class :character   1st Qu.:28.75   1st Qu.:4375  
 Mode  :character   Median :32.50   Median :4750  
                    Mean   :32.50   Mean   :4750  
                    3rd Qu.:36.25   3rd Qu.:5125  
                    Max.   :40.00   Max.   :5500  
> dim(veri)   # View the size of the data frame
[1] 4 3
> colnames(veri)  # Display column names in the data frame
[1] "Ad"   "Yas"  "Maas"  # Display columns in a data frame
> veri$Ad
[1] "Ahmet"  "Ayşe"   "Mehmet" "Fatma" 
> veri$Yas
[1] 25 30 35 40
> veri$Maas
[1] 4000 4500 5000 5500
> veri[veri$Yas > 30, ]  # Filtering a specific column in the data frame
      Ad Yas Maas
3 Mehmet  35 5000
4  Fatma  40 5500
> veri$Cinsiyet <- c("Erkek", "Kadın", "Erkek", "Kadın") # Add a new column to the data frame
> veri$Maas <- veri$Maas * 1.1  # Update data
> veri <- subset(veri, select = -Cinsiyet)  # Delete a specific column in a data frame
> write.csv(veri, file = "veri.csv", row.names = FALSE  # Writing data frame to file
> veri_oku <- read.csv("veri.csv")
> hist(veri_oku$Yas, main = "Yaş Dağılımı", xlab = "Yaş", ylab = "Frekans", col = "skyblue")  # Visualize data
> > ortalama_maas <- mean(veri$Maas)  # Calculate the average of columns in a data frame
> print(ortalama_maas)
[1] 5225
> standart_sapma_yas <- sd(veri$Yas)  # Calculate the standard deviation of columns in a data frame
> print(standart_sapma_yas)
[1] 6.454972
> max_yas <- max(veri$Yas)  # Finding maximum and minimum values in a data frame
> min_maas <- min(veri$Maas)
> print(paste("Maksimum Yaş:", max_yas))
[1] "Maksimum Yaş: 40"
> print(paste("Minimum Maaş:", min_maas))
[1] "Minimum Maaş: 4400"
> sirali_veri <- veri[order(veri$Yas), ]  # Sort a specific column in a data frame
> print(sirali_veri)
      Ad Yas Maas
1  Ahmet  25 4400
2   Ayşe  30 4950
3 Mehmet  35 5500
4  Fatma  40 6050
> ozel_satirlar <- veri[veri$Ad == "Ahmet", ]  # Filter rows containing a custom value in the data frame
> print(ozel_satirlar)
     Ad Yas Maas
1 Ahmet  25 4400
> veri$Yas <- as.factor(veri$Yas)  # Transform values in data frame
> print(veri$Yas)
[1] 25 30 35 40
Levels: 25 30 35 40
> any(is.na(veri))   # Checking for missing values in the data frame
[1] FALSE
> temiz_veri <- unique(veri)   # Remove duplicate rows in data frame
> birlesik_sutun <- paste(veri$Ad, veri$Yas, sep = ", ")   # Merge columns in data frame
> print(birlesik_sutun)
[1] "Ahmet, 25"  "Ayşe, 30"   "Mehmet, 35" "Fatma, 40" 
> gruplanmis_veri <- aggregate(Maas ~ Yas, data = veri, FUN = mean)  # Grouping and calculating summary statistics based on a specific column in the data frame
> print(gruplanmis_veri)
  Yas Maas
1  25 4400
2  30 4950
3  35 5500
4  40 6050
> filtreli_veri <- subset(veri, Yas == 35)   # Filter data based on a specific column in the data frame
> print(filtreli_veri)
      Ad Yas Maas
3 Mehmet  35 5500
> toplam_maas <- sum(veri$Maas)  # Calculate the sum of columns in a data frame
> print(toplam_maas)
[1] 20900
> 
