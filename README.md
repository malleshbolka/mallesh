import numpy as np

def calculate(list_input):
    # 1. Validation: The list must have exactly 9 elements
    if len(list_input) != 9:
        raise ValueError("List must contain nine numbers.")
    
    # 2. Reshape: Convert the flat 9-number list into a 3x3 matrix
    matrix = np.array(list_input).reshape(3, 3)
    
    # 3. Calculations: Compute stats for columns (axis=0), rows (axis=1), and flattened matrix
    calculations = {
        'mean': [
            matrix.mean(axis=0).tolist(),
            matrix.mean(axis=1).tolist(),
            matrix.mean().item()
        ],
        'variance': [
            matrix.var(axis=0).tolist(),
            matrix.var(axis=1).tolist(),
            matrix.var().item()
        ],
        'standard deviation': [
            matrix.std(axis=0).tolist(),
            matrix.std(axis=1).tolist(),
            matrix.std().item()
        ],
        'max': [
            matrix.max(axis=0).tolist(),
            matrix.max(axis=1).tolist(),
            matrix.max().item()
        ],
        'min': [
            matrix.min(axis=0).tolist(),
            matrix.min(axis=1).tolist(),
            matrix.min().item()
        ],
        'sum': [
            matrix.sum(axis=0).tolist(),
            matrix.sum(axis=1).tolist(),
            matrix.sum().item()
        ]
    }

    return calculations

# --- Test it out! ---
print(calculate([0, 1, 2, 3, 4, 5, 6, 7, 8]))
