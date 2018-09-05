

library("tidyverse")
str(surveys)
#select columns
select(surveys,species_id,weight)
#select rows
filter(surveys, year==1995)
# Pipes: %>% 
surveys %>% 
filter(year==1995) %>% 
select(species_id,weight)   
#select rows
exercise <- surveys %>% 
  filter(weight < 5) %>% 
  select(species_id,weight, sex)  


#create new column
#mutate()

data_with_kg <- surveys %>% 
  mutate(weight_kg=weight/1000)

surveys %>% 
  mutate(weight_kg=weight/1000, weight_kg2=weight_kg*2)

surveys %>% 
  mutate(weight_kg=weight/1000, weight_kg2=weight_kg*2) %>% head()


surveys %>% 
  filter(!is.na(weight)) %>% 
  mutate(weight_kg=weight/1000,weight_kg2=weight_kg*2) %>% head()

surveys %>% 
  group_by(sex) %>% 
  summarise(mean_weight= mean(weight,na.rm = TRUE))
#remove the missing values first (using filter), and re-run


#group by two columns
surveys %>% 
  filter(!sex=="") %>% 
  group_by(sex) %>% 
  summarise(mean_weight= mean(weight,na.rm = TRUE))


summarise_two <- surveys %>% 
  filter(!sex=="") %>% 
  filter(!is.na(weight)) %>% 
  group_by(sex,species_id) %>% 
  summarise(mean_weight=mean(weight))

#commands add a new column
#minumm weight (and maxim weight)

summarise_two <- surveys %>% 
  filter(!sex=="") %>% 
  filter(!is.na(weight)) %>% 
  group_by(sex,species_id) %>% 
  summarise(mean_weight=mean(weight), min_weight=min(weight))

#counting
surveys %>% 
  filter(!sex=="") %>% 
  count(sex)

#count with two variable
surveys %>% 
  filter(!sex=="") %>% 
  count(sex, species)

#sorting(arrange())
surveys %>% 
  filter(!sex=="") %>% 
  count(sex, species) %>% 
  arrange(species,desc(n))

#Reshaping the data



