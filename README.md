# ITSTEP-JAVA-HW20220919
add hw from 19/09/2022

task 
 Переписать императивным подходом(циклы, if-ы...):

 List<Human> humans = DataBase.getHumans();
        //Сгруппировать людей по специальности в разные коллекции.
        //Заранее мы не знаем сколько у нас специаольностей.
        //Результат нужно хранить в map(ключ-специальность, значение - список из human)

        Map<Speciality, List<Human>> map = humans
                .stream()
                .collect(Collectors.groupingBy(Human::getSpeciality));

        map.forEach(((speciality, group) -> {
            System.out.println(speciality);
            group.forEach(System.out::println);
        }));
