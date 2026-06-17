CODTECH-TASK 4 

# Open the file
file = open("netflix_titles.csv", "r", encoding="utf-8")

movies = 0
tv_shows = 0
year_count = {}

# Skip header line
file.readline()

for line in file:
    parts = line.strip().split(",")

    if len(parts) > 7:
        content_type = parts[1]
        release_year = parts[7]

        # Count Movies and TV Shows
        if content_type == "Movie":
            movies += 1
        elif content_type == "TV Show":
            tv_shows += 1

        # Count release years
        if release_year.isdigit():
            if release_year in year_count:
                year_count[release_year] += 1
            else:
                year_count[release_year] = 1

file.close()

# Print results
print("NETFLIX CONTENT ANALYSIS")
print("------------------------")
print("Total Movies:", movies)
print("Total TV Shows:", tv_shows)

print("\nTop 5 Release Years:")
sorted_years = sorted(year_count.items(), key=lambda x: x[1], reverse=True)

count = 0
for year, value in sorted_years:
    print(year, ":", value)
    count += 1
    if count == 5:
        break# 

Description:

Netflix Content Analysis is a simple Python-based project that reads and analyzes Netflix dataset using basic file handling techniques. It helps to understand the distribution of movies and TV shows, along with trends in release years.

🎯 Objective:
The main objective of this project is to:
Analyze Netflix content data using Python
Count and compare Movies and TV Shows
Identify most common release years
Learn basic data handling without using external libraries

⭐ Key Features:
Reads dataset using Python file handling
Counts total Movies and TV Shows
Analyzes release year frequency
Displays top release years
Fully implemented without any external libraries

🧑‍💻 Technology Used:
Python (Core programming)
File Handling (open, read, loop)
String operations (split, strip)
Dictionary for data counting
Basic sorting techniques