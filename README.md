# class-method-as-constructor


class Persons:
    count_instance = 0
    def __init__(self,first_name,last_name,age):
        Persons.count_instance += 1
        self.first_name = first_name
        self.last_name = last_name
        self.age = age


    @classmethod
    def full_string(cls,string):
        first,last,age = string.split(',')
        return cls(first,last,age)

    @classmethod
    def count_instances(cls):
        return f'you have created {cls.count_instance} instances of Person class'



    def full_name(self):
        return f'{self.first_name} {self.last_name}'


p1 = Persons('kamran','khan',24)
p2 = Persons('Aisha','Firdaus',23)
p3 = Persons.full_string('kishwar,khan,21')

# print(p1.full_name())

print(Persons.count_instances())

print(p3.full_name())
