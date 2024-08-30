# Python-Solution-for-Calculating-Minimum-Shots-for-a-Dominant-Basketball-Victory

Rahul and Riya are playing a game of basketball against each other, one-versus-one.
Currently, Rahul has A points, and Riya has B points. Each shot of a player can score either 2 or 3 points.
Rahul isn't just out to win - he wants to win in dominant fashion.
Rahul believes that his win is dominant if he ends the game with at least 10 points more than Riya.
If Rahul is able to prevent Riya from scoring any more points, what's the minimum number of shots he further needs to get a dominant victory?

Input
The first line of the input contains a single integer T, denoting the number of test cases.
The first line of each test case contains two space-separated integers A and B, denoting the scores of Rahul and Riya.

Constraints
1 ≤ T ≤ 104
2 ≤ A, B ≤ 100
Output
For each test case, output on a new line the minimum number of shots Rahul needs to win a dominant victory.

def min_shots_for_dominant_victory(T, test_cases):
    results = []
    for i in range(T):
        A, B = test_cases[i]
        target = B + 10
        points_needed = max(0, target - A)
        
        shots_needed = (points_needed + 2) // 3  
        
        results.append(shots_needed)
    
    return results

T = int(input())
test_cases = [tuple(map(int, input().split())) for _ in range(T)]

results = min_shots_for_dominant_victory(T, test_cases)
for result in results:
    print(result)
