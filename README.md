# dsci-100-group-project
DSCI-100-TERM-END-PROJECT

 
library(tidyverse)
Players_Data <- read.csv(url("https://drive.google.com/uc?export=download&id=1Mw9vW0hjTJwRWx0bDXiSpYsO3gKogaPz"))
Sessions_Data <- read.csv(url("https://drive.google.com/uc?export=download&id=14O91N5OlVkvdGxXNJUj5jIsV5RexhzbB"))

Players_Data_Edit <- Players_Data %>% select(experience, subscribe, hashedEmail, played_hours, name, gender, age)
Sessions_Data_Edit <- Sessions_Data %>% select(start_time, end_time, original_start_time, original_end_time) 

Players_Data_Edits <- Players_Data_Edit %>% filter(played_hours > 0) %>% mutate(log_scaled_hours = played_hours * log)
