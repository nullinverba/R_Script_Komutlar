#R Script Basic Commands

veri <- data.frame( 
    Ad = c("Ahmet", "Ayşe", "Mehmet", "Fatma"),
    Yas = c(25, 30, 35, 40),
    Maas = c(4000, 4500, 5000, 5500)
)  # Creating a data frame
print(veri)

summary(veri) # Summary of the data frame

dim(veri) # Viewing the size of the data frame

colnames(veri) # Displaying column names in the data frame

veri$Ad  # Display columns in a data frame
veri$Yas
veri$Maas

veri[veri$Yas > 30, ] # Filtering a specific column in the data frame

veri$Cinsiyet <- c("Erkek", "Kadın", "Erkek", "Kadın") # Add a new column to the data frame

veri$Maas <- veri$Maas * 1.1  # Update data

veri <- subset(veri, select = -Cinsiyet)  # Delete a specific column in a data frame

write.csv(veri, file = "veri.csv", row.names = FALSE)  # Writing data frame to file

veri_oku <- read.csv("veri.csv")
hist(veri_oku$Yas, main = "Yaş Dağılımı", xlab = "Yaş", ylab = "Frekans", col = "skyblue")  # Visualize data

ortalama_maas <- mean(veri$Maas) # Calculate the average of columns in a data frame
print(ortalama_maas)

standart_sapma_yas <- sd(veri$Yas)  # Calculate the standard deviation of columns in a data frame
print(standart_sapma_yas)

max_yas <- max(veri$Yas)  # Finding maximum and minimum values in a data frame
min_maas <- min(veri$Maas)
print(paste("Maksimum Yaş:", max_yas))
print(paste("Minimum Maaş:", min_maas))

sirali_veri <- veri[order(veri$Yas), ]  # Sort a specific column in a data frame
print(sirali_veri)

ozel_satirlar <- veri[veri$Ad == "Ahmet", ]  # Filter rows containing a custom value in the data frame
print(ozel_satirlar)

veri$Yas <- as.factor(veri$Yas)  # Transform values in data frame
print(veri$Yas)

any(is.na(veri))  # Checking for missing values in the data frame

temiz_veri <- unique(veri)  # Remove duplicate rows in data frame

birlesik_sutun <- paste(veri$Ad, veri$Yas, sep = ", ")  # Merge columns in data frame
print(birlesik_sutun)

gruplanmis_veri <- aggregate(Maas ~ Yas, data = veri, FUN = mean)  # Grouping and calculating summary statistics based on a specific column in the data frame
print(gruplanmis_veri)

filtreli_veri <- subset(veri, Yas == 35)  # Filter data based on a specific column in the data frame
print(filtreli_veri)


toplam_maas <- sum(veri$Maas)  # Calculate the sum of columns in a data frame
print(toplam_maas)
