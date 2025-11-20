import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
np.random.seed(42)

customer_x = np.random.randint(70, 120, 50)   # Customer location X
customer_y = np.random.randint(15, 40, 50)    # Customer location Y
spending_score = np.random.randint(0, 3000, 50)   # Spending score

fig = plt.figure(figsize=(10, 7))
ax = fig.add_subplot(111, projection='3d')

colors = plt.cm.tab20(np.linspace(0, 1, len(customer_x)))

for i in range(len(customer_x)):
    ax.plot([customer_x[i], customer_x[i]], 
            [customer_y[i], customer_y[i]], 
            [0, spending_score[i]],
            color=colors[i],
            linewidth=2)

ax.scatter(customer_x, customer_y, spending_score, 
           color='steelblue', 
           s=80,
           edgecolor='black')

ax.set_xlabel('Customer Location X', fontsize=12)
ax.set_ylabel('Customer Location Y', fontsize=12)
ax.set_zlabel('Spending Score', fontsize=12)

ax.set_title("3D Customer Segmentation Visualization", fontsize=15)

plt.show()


