from tkinter import *

root = Tk()
root.title("IPL Season 13 Live Score |Group 4 (Roll no- 32,36,42) ")

url = 'https://www.cricbuzz.com/'
import requests
from bs4 import BeautifulSoup


def Get_data(data):
    team1, team2, team1_score, team2_score = data
    page = requests.get(url)
    soup = BeautifulSoup(page.text, 'html.parser')
    team_1 = soup.find_all(class_ = "cb-ovr-flo cb-hmscg-tm-nm")[0].get_text()
    team_2 = soup.find_all(class_ = "cb-ovr-flo cb-hmscg-tm-nm")[1].get_text()

    team_1_score = soup.find_all(class_ = "cb-ovr-flo")[8].get_text()
    team_2_score = soup.find_all(class_ = "cb-ovr-flo")[10].get_text()
    team1.config(text = team_1)
    team2.config(text = team_2)
    team1_score.config(text = team_1_score)
    team2_score.config(text = team_2_score)


a = Label(root, text = ' IPL 2020 Season 13 ', font = (" ", 40))
a.grid(row = 0, columnspan = 2)
team1 = Label(root, text = "Team 1", font = (" ", 20))
team1.grid(row = 1, column = 0)
team2 = Label(root, text = "Team 2", font = (" ", 20))
team2.grid(row = 1, column = 1)

team1_score = Label(root, text = "hit refresh", font = (" ", 20))
team1_score.grid(row = 2, column = 0)
team2_score = Label(root, text = "hit refresh", font = (" ", 20))
team2_score.grid(row = 2, column = 1)
data = [team1, team2, team1_score, team2_score]
refresh = Button(root, text = 'Refresh',
                 command = lambda: Get_data(data),
                 height = 2, width = 10, font = ('', 20))
refresh.grid(row = 3, columnspan = 2)
root.mainloop()
