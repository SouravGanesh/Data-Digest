𝟭. 𝗟𝗶𝗻𝗲𝗮𝗿 𝗥𝗲𝗴𝗿𝗲𝘀𝘀𝗶𝗼𝗻: Imagine you want to predict the price of a house based on its size. Linear regression helps you find the straight-line relationship between size and price.

𝟮. 𝗟𝗼𝗴𝗶𝘀𝘁𝗶𝗰 𝗥𝗲𝗴𝗿𝗲𝘀𝘀𝗶𝗼𝗻: Contrary to what the name suggests, this is actually for classification tasks. It helps you decide if an email is spam or not by calculating the probability.

𝟯. 𝗗𝗲𝗰𝗶𝘀𝗶𝗼𝗻 𝗧𝗿𝗲𝗲𝘀: These are like flowcharts that lead you to a decision by asking a series of questions based on the data's features.

𝟰. 𝗥𝗮𝗻𝗱𝗼𝗺 𝗙𝗼𝗿𝗲𝘀𝘁: This one builds a whole 'forest' of decision trees and merges them to get more accurate and stable predictions.

𝟱. 𝗦𝘂𝗽𝗽𝗼𝗿𝘁 𝗩𝗲𝗰𝘁𝗼𝗿 𝗠𝗮𝗰𝗵𝗶𝗻𝗲𝘀 (𝗦𝗩𝗠): If your data points are apples and oranges, SVM finds the best line that separates the apples from the oranges.

𝟲. 𝗞-𝗡𝗲𝗮𝗿𝗲𝘀𝘁 𝗡𝗲𝗶𝗴𝗵𝗯𝗼𝗿𝘀 (𝗞𝗡𝗡): This algorithm looks at the closest data points, like neighbors, to decide the category of a new point.

𝟳. 𝗡𝗮𝗶𝘃𝗲 𝗕𝗮𝘆𝗲𝘀: It's based on probability and is really good for things like filtering spam or analyzing sentiment.

𝟴. 𝗚𝗿𝗮𝗱𝗶𝗲𝗻𝘁 𝗕𝗼𝗼𝘀𝘁𝗶𝗻𝗴 𝗠𝗮𝗰𝗵𝗶𝗻𝗲𝘀 (𝗚𝗕𝗠): This is like a smart assembly line, where each new machine corrects the mistakes of the previous one to improve results.

![ML Cheetsheet](images/ml_cheeetsheet.png)

𝗗𝗮𝘁𝗮 𝗠𝗼𝗱𝗲𝗹𝗶𝗻𝗴 - 𝗧𝗵𝗲 𝗕𝗹𝘂𝗲𝗽𝗿𝗶𝗻𝘁 𝗳𝗼𝗿 𝗗𝗮𝘁𝗮 𝗦𝘂𝗰𝗰𝗲𝘀𝘀

Data Modeling is the art and science of creating a structured framework to handle the influx and storage of data. It's like the architectural blueprint of your data environment, ensuring efficiency, consistency, and scalability. In essence, it's your roadmap for data success.

📘 𝗖𝗼𝗿𝗲 𝗖𝗼𝗻𝗰𝗲𝗽𝘁𝘀 𝗶𝗻 𝗜𝗻𝗳𝗼𝗿𝗺𝗮𝘁𝗶𝗼𝗻 𝗠𝗼𝗱𝗲𝗹𝗶𝗻𝗴
𝗦𝗰𝗵𝗲𝗺𝗮: This acts as the guidebook for your database, defining how information is structured and establishing the connections between different data fragments.
𝗙𝗮𝗰𝘁 𝗧𝗮𝗯𝗹𝗲: This serves as the central storage 🏦 for all the essential metrics and performance indicators. It's the nucleus of your data cosmos.
𝗗𝗶𝗺𝗲𝗻𝘀𝗶𝗼𝗻 𝗧𝗮𝗯𝗹𝗲𝘀: Encircling your fact table, these tables contain illustrative, textual, or categorial details. Consider them as the backdrop to your metrics.

🌟 𝗧𝘄𝗼 𝗠𝗮𝗶𝗻 𝗧𝘆𝗽𝗲𝘀 𝗼𝗳 𝗗𝗮𝘁𝗮 𝗗𝗲𝘀𝗶𝗴𝗻 𝗶𝗻 𝗗𝗮𝘁𝗮 𝗪𝗮𝗿𝗲𝗵𝗼𝘂𝘀𝗲𝘀

1. 𝗦𝘁𝗮𝗿 𝗦𝗰𝗵𝗲𝗺𝗮 🌟
𝗪𝗵𝗮𝘁 𝗶𝘀 𝗶𝘁?: In a Star Schema, the fact table takes its central position, directly linked to various dimension tables.
𝗣𝗿𝗼𝘀: Extremely user-friendly and ensures rapid query performances.
𝗖𝗼𝗻𝘀: Potential data redundancy issues.

2. 𝗦𝗻𝗼𝘄𝗳𝗹𝗮𝗸𝗲 𝗦𝗰𝗵𝗲𝗺𝗮 ❄️
𝗪𝗵𝗮𝘁 𝗶𝘀 𝗶𝘁?: The Snowflake Schema elevates it a notch by normalizing dimension tables into sub-dimensions, forming a hierarchy.
𝗣𝗿𝗼𝘀: Highly normalized, minimizing data redundancy.
𝗖𝗼𝗻𝘀: More intricate queries and potential sluggishness.

𝗦𝗼, 𝗪𝗵𝗶𝗰𝗵 𝗢𝗻𝗲 𝘁𝗼 𝗖𝗵𝗼𝗼𝘀𝗲?
𝗚𝗼 𝗦𝘁𝗮𝗿 🌟: If you're after simplicity and quicker query outcomes.
𝗣𝗶𝗰𝗸 𝗦𝗻𝗼𝘄𝗳𝗹𝗮𝗸𝗲 ❄️: If you're concerned about data storage and normalization.

![Cheetsheet](images/shema_cheeetsheet.png)
