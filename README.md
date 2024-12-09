import os
import datetime

# Directory containing your GitHub repository
repo_path = "path_to_your_local_repository"  # Replace with the local path to your repo

# Function to create or update a dummy file
def update_file():
    os.chdir(repo_path)  # Navigate to your repository directory
    with open("activity.txt", "a") as f:  # Open or create a file
        f.write(f"Commit made on {datetime.datetime.now()}\n")  # Add a timestamp

# Function to commit and push changes
def commit_and_push():
    os.system("git add .")
    os.system('git commit -m "Automated daily commit"')
    os.system("git push origin main")

# Run the functions
update_file()
commit_and_push()
print("Daily commit made!")

