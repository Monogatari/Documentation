# Ren'py

If you already have a Ren'py game and would like to export it to Monogatari, you can do it very easily. As you may have seen the syntax is pretty much the same so you'll only need to change some letters, add some commas and you'll be ready to go!

You can take a look to the script of The Question in [Ren'py](http://www.renpy.org/doc/html/thequestion.html) and this Monogatari Script so you can compare and learn more! If you want, you can also [download the full The Question game made in Monogatari here](https://web.tresorit.com/l#rVQ-obo0UOwTP59dSS6doA).

```
// Define the backgrounds for each scene.
const scenes = {
	"lecturehall": "lecturehall.jpg",
	"uni": "uni.jpg",
	"meadow": "meadow.jpg",
	"club": "club.jpg"
};

// Define the Characters
const characters = {
	"s":{
		"Name": "Sylvie",
		"Color": "#c8ffc8",
		"Images":{
			"normal-green": "sylvie-green-normal.png",
			"giggle-green": "sylvie-green-giggle.png",
			"smile-green": "sylvie-green-smile.png",
			"surprised-green": "sylvie-green-surprised.png",
			"normal-blue": "sylvie-blue-normal.png",
			"giggle-blue": "sylvie-blue-giggle.png",
			"smile-blue": "sylvie-blue-smile.png",
			"surprised-blue": "sylvie-blue-surprised.png",
		}
	},

	"m":{
		"Name": "Me",
		"Color": "#c8c8ff"
	}
};

let script = {
	// The game starts here.
	"Start":[

		"play music illurock.ogg loop",
		"scene lecturehall with fadeIn",
		"It's only when I hear the sounds of shuffling feet and supplies being put away that I realize that the lecture's over.",
		"Professor Eileen's lectures are usually interesting, but today I just couldn't concentrate on it.",
		"I've had a lot of other thoughts on my mind...thoughts that culminate in a question.",
		"It's a question that I've been meaning to ask a certain someone.",
		"scene uni with fadeIn",
		"When we come out of the university, I spot her right away.",
		"show s normal-green with fadeIn",
		"I've known Sylvie since we were kids. She's got a big heart and she's always been a good friend to me.",
		"But recently... I've felt that I want something more.",
		"More than just talking, more than just walking home together when our classes end.",
		{"Choice":{
			"Text": "As soon as she catches my eye, I decide...",
			"RightAway": {
			  "Text": "... to ask her right away.",
			  "Do": "jump rightaway"
			},
			"Later":{
			  "Text": "... to ask her later.",
			  "Do": "jump later"
			}
		}}

	],

	"rightaway":[

		"show s smile-green",
		"s Hi there! How was class?",
		"m Good...",
		"I can't bring myself to admit that it all went in one ear and out the other.",
		"m Are you going home now? Wanna walk back with me?",
		"s Sure!",
		"scene meadow with fadeIn",
		"After a short while, we reach the meadows just outside the neighborhood where we both live.",
		"It's a scenic view I've grown used to. Autumn is especially beautiful here.",
		"When we were children, we played in these meadows a lot, so they're full of memories.",
		"m Hey... Umm...",
		"show s smile-green with fadeIn",
		"She turns to me and smiles. She looks so welcoming that I feel my nervousness melt away.",
		"I'll ask her...!",
		"m Ummm... Will you...",
		"m Will you be my artist for a visual novel?",
		"show s surprised-green with fadeIn",
		"Silence.",
		"She looks so shocked that I begin to fear the worst. But then...",
		"show s smile-green with fadeIn",
		{"Choice":{
			"Text": "s Sure, but what is a \"visual novel?\"",
			"VN":{
				"Text": "It's a videogame.",
				"Do": "jump game"
			},
			"Hentai":{
				"Text": "It's an interactive book.",
				"Do": "jump book"
			}

		}}
	],

	"game": [
		"m It's a kind of videogame you can play on your computer or a console.",
		"m Visual novels tell a story with pictures and music.",
		"m Sometimes, you also get to make choices that affect the outcome of the story.",
		"s So it's like those choose-your-adventure books?",
		"m Exactly! I've got lots of different ideas that I think would work.",
		"m And I thought maybe you could help me...since I know how you like to draw.",
		"m It'd be hard for me to make a visual novel alone.",
		"show s normal-green with fadeIn",
		"s Well, sure! I can try. I just hope I don't disappoint you.",
		"m You know you could never disappoint me, Sylvie.",
		"jump marry"
	],

	"book": [
		function () {
			storage.book = true;
			return true;
		},
		"m It's like an interactive book that you can read on a computer or a console.",
		"show s surprised-green",
		"s Interactive?",
		"m You can make choices that lead to different events and endings in the story.",
		"s So where does the \"visual\" part come in?",
		"m Visual novels have pictures and even music, sound effects, and sometimes voice acting to go along with the text.",
		"show s smile-green",
		"s I see! That certainly sounds like fun. I actually used to make webcomics way back when, so I've got lots of story ideas.",
		"m That's great! So...would you be interested in working with me as an artist?",
		"s I'd love to!",
		"jump marry"
	],

	"marry":[
		"scene black with fadeIn",
		"And so, we become a visual novel creating duo.",
		"scene club with fadeIn",
		"Over the years, we make lots of games and have a lot of fun making them.",
		{"Conditional":{
			"Condition": function () {
				return storage.book;
			},
			"True": "Our first game is based on one of Sylvie's ideas, but afterwards I get to come up with stories of my own, too.",
			"False": "next"
		}},

		"We take turns coming up with stories and characters and support each other to make some great games!",
		"And one day...",
		"show s normal-blue with fadeIn",
		"s Hey...",
		"m Yes?",
		"show s giggle-blue with fadeIn",
		"s Will you marry me?",
		"m What? Where did this come from?",
		"show s surprised-blue",
		"s Come on, how long have we been dating?",
		"m A while...",
		"show s smile-blue",
		"s These last few years we've been making visual novels together, spending time together, helping each other...",
		"s I've gotten to know you and care about you better than anyone else. And I think the same goes for you, right?",
		"m Sylvie...",
		"show sylvie blue giggle-blue",
		"s But I know you're the indecisive type. If I held back, who knows when you'd propose?",
		"show s normal-blue",
		"s So will you marry me?",
		"m Of course I will! I've actually been meaning to propose, honest!",
		"s I know, I know.",
		"m I guess... I was too worried about timing. I wanted to ask the right question at the right time.",
		"show s giggle-blue",
		"s You worry too much. If only this were a visual novel and I could pick an option to give you more courage!",
		"scene black with dissolve-blue",
		"We get married shortly after that.",
		"Our visual novel duo lives on even after we're married...and I try my best to be more decisive.",
		"Together, we live happily ever after even now.",
		"<b>Good Ending</b>.",
		"end"

	],

	"later":[
		"I can't get up the nerve to ask right now. With a gulp, I decide to ask her later.",
		"scene black with fadeIn",
		"But I'm an indecisive person.",
		"I couldn't ask her that day and I end up never being able to ask her.",
		"I guess I'll never know the answer to my question now...",
		"<b>Bad Ending</b>.",
		"end"
	]
};
```

