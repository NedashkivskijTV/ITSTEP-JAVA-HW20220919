# ITSTEP-JAVA-HW20220919
add hw from 19/09/2022

task 
 Переписать императивным подходом(циклы, if-ы...):

 List<Human> humans = DataBase.getHumans();
        //Сгруппировать людей по специальности в разные коллекции.
        //Заранее мы не знаем сколько у нас специаольностей.
        //Результат нужно хранить в map(ключ-специальность, значение - список из human)

//        Map<String, Integer> cities = new HashMap<>();
//        cities.put("Zp", 746_749);
//        cities.put("Km", 265_693);
//        cities.put("Zt", 266_106);
//        System.out.println(cities.get("Zp"));

        Map<Speciality, List<Human>> map = humans
                .stream()
                .collect(Collectors.groupingBy(Human::getSpeciality));

        map.forEach(((speciality, group) -> {
            System.out.println(speciality);
            group.forEach(System.out::println);
        }));
