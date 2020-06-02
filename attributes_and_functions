class Attributes(object):
    def __init__(self, name, weight, val):
        self.name = name
        self.cost = weight
        self.value = val

    def get_Value(self):
        return self.value
    def get_Cost(self):
        return self.cost
    def get_Name(self):
        return self.name
    def get_density(self):
        return self.get_Value()/self.get_Cost()
    def __str__(self):
        return self.name + ': <' + str(self.value) + ',' + str(self.cost) + '>'

def make_tuples(names, weights, values):
    options = []
    for i in range(len(names)):
        options.append(Attributes(names[i], weights[i], values[i]))
    return options

def greedy_solve(items, upperbound, keyFunction):
    items_copy = sorted(items, key = keyFunction, reverse = True)  #O(nlogn)
    result = []
    totalCost , totalValue = 0 , 0
    for i in range(len(items_copy)):                         #O(n)
        if(totalCost + items_copy[i].get_Cost() <= upperbound):
            result.append(items_copy[i])
            totalCost+=items_copy[i].get_Cost()
            totalValue+=items_copy[i].get_Value()
    return (result,totalValue)

def test(items, max, keyFunction):
    backpack , value = greedy_solve(items, max, keyFunction)
    for things in backpack:
        print('Items:' , things)
    print('Total Value: ', value)
