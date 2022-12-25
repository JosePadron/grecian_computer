# Ring numbers per slot
ring_1 = [[8, 9, 15, 14], [8, 4, 4, 11], [3, 4, 5, 11], [4, 6, 6, 14], [12, 6, 7, 11], [2, 3, 8, 14], [
    5, 3, 9, 11], [10, 14, 10, 14], [7, 14, 11, 14], [16, 21, 12, 11], [8, 21, 13, 14], [7, 9, 14, 11]]
ring_2 = [[12, 2, 6, 0], [0, 13, 0, 0], [6, 9, 14, 0], [0, 0, 12, 0], [10, 17, 3, 0], [0, 19, 8, 0], [
    10, 3, 9, 0], [0, 12, 0, 0], [1, 3, 9, 0], [0, 26, 20, 0], [9, 6, 12, 0], [0, 0, 3, 0]]
ring_3 = [[0, 5, 21, 9], [0, 0, 6, 13], [0, 10, 15, 9], [0, 0, 4, 7], [0, 8, 9, 13], [0, 0, 18, 21], [
    0, 22, 11, 17], [0, 0, 26, 4], [0, 16, 14, 5], [0, 0, 1, 0], [0, 9, 12, 7], [0, 0, 0, 8]]
ring_4 = [[0, 0, 15, 6], [0, 0, 0, 0], [0, 0, 0, 11], [0, 0, 14, 11], [0, 0, 0, 6], [0, 0, 9, 11], [
    0, 0, 0, 0], [0, 0, 12, 6], [0, 0, 0, 17], [0, 0, 4, 7], [0, 0, 0, 3], [0, 0, 7, 0]]
ring_5 = [[0, 0, 0, 6], [0, 0, 0, 0], [0, 0, 0, 10], [0, 0, 0, 0], [0, 0, 0, 7], [0, 0, 0, 0], [
    0, 0, 0, 15], [0, 0, 0, 0], [0, 0, 0, 8], [0, 0, 0, 0], [0, 0, 0, 3], [0, 0, 0, 0]]

number_of_slots = len(ring_1)

# Check if sum is 42 and returns combination
def sum_is_valid(items):
    result = 0
    combination = [0, 0, 0, 0]
    for index in range(4):
        for item in items:
            if item[index] != 0:
                combination[index] = item[index]
                result = result + item[index]
                break

    if result == 42:
        return True, combination

    return False, combination


# Brute force to find valid combinations
try:
    for item_1_index, item_1 in enumerate(ring_1[:]):
        for item_2_index, item_2 in enumerate(ring_2[:]):
            for item_3_index, item_3 in enumerate(ring_3[:]):
                for item_4_index, item_4 in enumerate(ring_4[:]):
                    for item_5_index, item_5 in enumerate(ring_5[:]):
                        valid_combinations = 0
                        combinations = []

                        # Look for continuos valid combinations
                        for index in range(number_of_slots):
                            result, combination = sum_is_valid(
                                [ring_5[(item_5_index + index) % number_of_slots],
                                 ring_4[(item_4_index + index) % number_of_slots],
                                 ring_3[(item_3_index + index) % number_of_slots],
                                 ring_2[(item_2_index + index) % number_of_slots],
                                 ring_1[(item_1_index + index) % number_of_slots]])
                            if result:
                                if combination not in combinations:
                                    combinations.append(combination)
                                    valid_combinations = valid_combinations + 1
                            else:
                                break

                        if valid_combinations == number_of_slots:
                            print("Solution:")
                            for combination in combinations:
                                print(combination)
                            raise StopIteration
except StopIteration:
    pass
