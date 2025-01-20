def arithmetic_arranger(problems, show_answers=False):
   
    def checker(problems):
        invalid = ("*", "/")
        if len(problems) > 5:
            print('Error: Too many problems.')
            return 'Error: Too many problems.'
        for problem in problems:
            for op in invalid:
                if op in problem:
                    print("Error: Operator must be '+' or '-'.")
                    return "Error: Operator must be '+' or '-'."
            parts = problem.split()
            if len(parts) != 3:
                return None
            num1, op, num2 = parts
            if len(num1) > 4 or len(num2) > 4:
                print('Error: Numbers cannot be more than four digits.')
                return 'Error: Numbers cannot be more than four digits.'
            if not num1.isdigit() or not num2.isdigit():
                print('Error: Numbers must only contain digits.')
                return 'Error: Numbers must only contain digits.'
        else:
            return problems

    result = checker(problems)
    if isinstance(result, str):
        return result

    if result == problems:
        def arranger_function(problems):
            top_row = []
            middle_row = []
            bottom_row = []
            solution_row = []
            for problem in problems:
                num1, op, num2 = problem.split()
                if len(num1) > len(num2):
                    width = len(num1) + 2
                else:
                    width = len(num2) + 2
                top_row.append(num1.rjust(width))
                bottom_row.append('-' * width)
                middle_row.append(op + num2.rjust(width - 1))
                if show_answers == True:
                    int1 = int(num1)
                    int2 = int(num2)
                    if op == '+':
                        solution = int1 + int2
                    else:
                        solution = int1 - int2
                    solution = str(solution)
                    solution_row.append(solution.rjust(width))
                    
            print('    '.join(top_row))
            print('    '.join(middle_row))
            print('    '.join(bottom_row))
            print('    '.join(solution_row))

            arranged_problems = '    '.join(top_row) + '\n' + '    '.join(middle_row) + '\n' + '    '.join(bottom_row)
            if show_answers:
                arranged_problems += '\n' + '    '.join(solution_row)
                return arranged_problems
            return arranged_problems

        return arranger_function(problems)
        
arithmetic_arranger(["3801 - 2", "123 + 49"])
