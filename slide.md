class: middle, center, title-slide

# Challenges on AT for Video


<br><br>
René Vidal <br>
Johns Hopkins University
---

# Outline

- Show sensitivity of attack quality to PGD parameters (step size, number of iterations).
- Show linear relationship between attack strength and PGD step size
- Show that better attacks do not lead to better defenses, so need to choose suboptimal PGD parameters
- Show that there is a need for a schedule on the attack strength, with small epsilon in first epochs, and large epsilon later, to achieve better defenses for all epsilons.

---

class: middle

# Standard training:

We use the 3D-ResNext-101 model as a backbone for the video classification.​

- Pretrained on Kinetics-400, finetuned on UCF-101-64​

- Train accuracy: top-1=90.98%; top-5=98.67%​

- Test accuracy: top-1=93.58%;  top-5=99.3%​
---

class: middle

# Video attacks:​

- Attack is known at testing time​

- L∞ attacks: Projected Gradient Descent (PGD)​

  - Adversarial example:
    <img src="https://render.githubusercontent.com/render/math?math=e^{i \pi} = -1">
  - Iterative perturbation:​
    <img src="https://render.githubusercontent.com/render/math?math=e^{i \pi} = -1">
    - ‘i’ indicates the ith iteration; α is the step size.​
---


class: middle

# Sensitivity of attack quality to PGD parameters 


---


class: middle

.width-45[![](https://i.pinimg.com/originals/4d/72/77/4d727788e093eeb1855d1efce67b8dc2.png)]&nbsp;&nbsp;&nbsp;
.width-45[![](https://i.pinimg.com/736x/77/f6/5e/77f65e6b161693dfeb722f3c1b71f301.jpg)] <br/>
.width-45[![](https://i2.wp.com/1.bp.blogspot.com/-kzqcwGQ4flI/YAkiLUCg1iI/AAAAAAAAEdM/Pl3BHqINiF4rNvajVcs-ChtahZ6DQ9jJwCLcBGAsYHQ/s16000/)]&nbsp;&nbsp;&nbsp;
.width-45[![](https://i.pinimg.com/originals/68/16/30/681630b5d8c403de2a8b71e5e9eaa25a.jpg)]

---

class: middle, center

.width-50[![](figures/lec0/terminator.png)]

"With artificial intelligence we are summoning the demon" -- Elon Musk

.width-45[![](https://thumbor.forbes.com/thumbor/960x0/https%3A%2F%2Fspecials-images.forbesimg.com%2Fimageserve%2F605f79eaad8970188040f338%2F960x0.jpg%3Ffit%3Dscale)]&nbsp;&nbsp;&nbsp;
.width-50[![](https://i.pinimg.com/originals/b3/b6/6f/b3b66f29ad734364dc277ce5bc897904.jpg)]

Triggers a rich imagination fueled by science-fiction.

---

class: middle, center
.width-40[![](figures/lec0/washing-machine.png)]&nbsp;&nbsp;&nbsp;
.width-55[![](https://miro.medium.com/max/500/1*pIdFZ54mJqKDhGKmZ-1UdQ.png)]


"We're really closer to a smart washing machine than Terminator. If you look at today's AI, we're really very nascent. I am really excited and passionate about AI's potential." -- Fei-Fei Li, Director of Stanford AI Lab.

???

The reality is quite different...

---

class: middle

.center[

.width-25.circle[![](figures/lec0/dijkstra.jpg)]&nbsp;&nbsp;&nbsp;
.width-25.circle[![](figures/lec0/valiant.jpg)]


]

Edsger Dijkstra: .italic[What do you work on?]<br>
Leslie Valiant (very proudly): .italic[Artificial Intelligence.]<br>
Edsger Dijkstra: .italic[Why don't you work first on the .bold["Intelligence"] part?]

???

Before trying to define the contours of artificial intelligence, let us first reflect on the these words.

-> No more "artificial"

---

class: middle

.width-30.circle.center[![](figures/lec0/minsky.png)]

.italic[".bold[What is intelligence, anyway?] It is only a word that people use to name those unknown processes with which our brains
solve problems we call hard. But whenever you learn a skill yourself, you're less impressed or mystified when other people
do the same.

This is why .bold[the meaning of "intelligence" seems so elusive]: it describes not some definite thing but only the
momentary horizon of .bold[our ignorance about how minds might work]. It is hard for scientists who try to understand intelligence
to explain precisely what they do, since our working definitions change from year to year. But it is not at all unusual for
sciences to aim at moving targets." -- Marvin Minsky]

???

-> No more "intelligence"

---

class: middle
.slide_left.width-110[![](figures/lec0/AI_0.png)]
---

# A definition?

Artificial intelligence is the science of making machines or programs that:
.center.grid[
.kol-1-4[]
.kol-1-4[
.caption[Think like people]
.width-100[![](figures/lec0/ai-think-people.png)]
]
.kol-1-4[
.caption[Think rationally]
.width-100[![](figures/lec0/ai-think-rationally.png)]]
]
.grid[
.kol-1-4[]
.kol-1-4[
.caption[Act like people]
.width-100[![](figures/lec0/ai-act-people.png)]
]
.kol-1-4[
.caption[Act rationally]
.width-100[![](figures/lec0/ai-act-rationally.png)]
]
]

.footnote[Image credits: [CS188](https://inst.eecs.berkeley.edu/~cs188/), UC Berkeley.]

???

Textbook definition(s) from AIMA.
---
class: middle
.slide_left.width-110[![](figures/lec0/AI_1.png)]
---
class: middle
# History of AI
.slide_left.width-110[![](figures/lec0/history_1.png)]
---
class: middle
# History of AI
.slide_left.width-110[![](figures/lec0/history_2.png)]
---
class: middle
# History of AI
.slide_left.width-110[![](figures/lec0/history_3.png)]
---
class: middle
# History of AI
.slide_left.width-110[![](figures/lec0/history_4.png)]
---
class: middle
# History of AI
.slide_left.width-110[![](figures/lec0/history_5.png)]
---
class: middle
# History of AI
.slide_left.width-110[![](figures/lec0/history_6.png)]
---
class: middle
# History of AI
.slide_left.width-110[![](figures/lec0/history_7.png)]
---
class: middle
# History of AI
.slide_left.width-110[![](figures/lec0/history_8.png)]
---
class: middle
# History of AI
.slide_left.width-110[![](figures/lec0/history_9.png)]
---
class: middle
# History of AI
.slide_left.width-110[![](figures/lec0/history_10.png)]


---
class: middle
# Types of AI
.slide_left.width-110[![](figures/lec0/ANI.png)]
---
class: middle
# Types of AI
.slide_left.width-110[![](figures/lec0/AGI.png)]
---
class: middle
# Types of AI
.slide_left.width-110[![](figures/lec0/ASI.png)]
---
class: middle
# Demand for AI
.slide_left.width-110[![](figures/lec0/AI_demand.png)]
---
class: middle, center
# Why should you care?

.width-80[![](https://www.mckinsey.com/~/media/mckinsey/industries/public%20and%20social%20sector/our%20insights/what%20the%20future%20of%20work%20will%20mean%20for%20jobs%20skills%20and%20wages/svg_workfuture_v9_ex5_rj.svgz)]


---
class: middle
# Domains of AI
.slide_left.width-110[![](figures/lec0/AI_domains.png)]

---

class: middle
# Machine Learning

.center[
.width-40[![](figures/lec7/cat.jpg)] &nbsp; &nbsp;
.width-40[![](figures/lec7/dog.jpg)]
]

.exercise[How would you write a computer program that recognizes cats from dogs?]

---

class: middle

.center.width-60[![](figures/lec7/cat1.png)]

---

count: false
class: black-slide, middle

.center.width-50[![](figures/lec7/cat2.png)]

.center[The good old-fashioned approach.]

---

count: false
class: black-slide, middle

.center.width-80[![](figures/lec7/cat3.png)]

---

count: false
class: black-slide, middle

.center.width-80[![](figures/lec7/cat4.png)]

---

class: middle

.center.width-100[![](figures/lec7/catordog-flow.gif)]

.center[The deep learning approach.]

---
class: middle
# Machine Learning
.slide_left.width-110[![](figures/lec0/ML.png)]
---
class: middle
# Machine Learning
.slide_left.width-110[![](figures/lec0/ML_features.png)]
---
class: middle
# Need for Machine Learning
.slide_left.width-110[![](figures/lec0/ML_need_1.png)]
---
class: middle
# Need for Machine Learning
.slide_left.width-110[![](figures/lec0/ML_need_0.png)]
---
class: middle
# Programming Languages for AI
.slide_left.width-110[![](figures/lec0/AI_prog.png)]

---
# What can AI do at present?

- Translate spoken Chinese to spoken English, live?
- Answer multi choice questions, as good as an 8th grader?
- Converse with a person for an hour?
- Play decently at Chess? Go? Poker? Soccer?
- Buy groceries on the web? in a supermarket?
- Prove mathematical theorems?
- Drive a car safely on a parking lot? in New York?
- Perform a surgery?
- Identify skin cancer better than a dermatologist?
- Write a funny story?
- Paint like Vangogh? Compose music?
- Show common sense?

---

class: middle, center, black-slide

<iframe width="600" height="450" src="https://www.youtube.com/embed/Nu-nlQqFCKg?rel=0" frameborder="0" allowfullscreen></iframe>

Speech translation and synthesis (2012)

---

class: middle, center, black-slide

<iframe width="600" height="450" src="https://www.youtube.com/embed/7gh6_U7Nfjs?rel=0" frameborder="0" allowfullscreen></iframe>

Speech synthesis and question answering (Google, 2018)

---

class: middle, center, black-slide

<iframe width="600" height="450" src="https://www.youtube.com/embed/V1eYniJ0Rnk?rel=0" frameborder="0" allowfullscreen></iframe>

Playing Atari games

---

class: middle, center, black-slide

<iframe width="600" height="450" src="https://www.youtube.com/embed/g-dKXOlsf98?rel=0" frameborder="0" allowfullscreen></iframe>

Beat the best human Go players (2016)

---

class: middle, center, black-slide

<iframe width="600" height="450" src="https://www.youtube.com/embed/NlpS-DhayQA?rel=0" frameborder="0" allowfullscreen></iframe>

Solving impactful and challenging problems

---

class: middle, center, black-slide

<iframe width="600" height="450" src="https://www.youtube.com/embed/yyLa6xIK9Qs?rel=0" frameborder="0" allowfullscreen></iframe>

Playing soccer (2018)

---

class: middle, center, black-slide

<iframe width="600" height="450" src="https://www.youtube.com/embed/V-M5SVta2uw?rel=0" frameborder="0" allowfullscreen></iframe>

A conversation with GPT-3 (2020)

---
class: middle, center, black-slide

<iframe width="600" height="450" src="https://www.youtube.com/embed/gn4nRCC9TwQ?rel=0" frameborder="0" allowfullscreen></iframe>

Learning to walk (2017)

???

Single algorithm for learning! Nothing is hardcoded.

Similar to a baby learning to walk.

---

class: middle, center, black-slide

<iframe width="600" height="450" src="https://www.youtube.com/embed/qhUvQiKec2U?rel=0" frameborder="0" allowfullscreen></iframe>

Driving a car (NVIDIA, 2016)

---

class: middle, center, black-slide

<iframe width="600" height="450" src="https://www.youtube.com/embed/RCahWWOSxaw?rel=0" frameborder="0" allowfullscreen></iframe>

... and preventing accidents.

---

class: middle, center, black-slide

<iframe width="600" height="450" src="https://www.youtube.com/embed/5kpsZoKjPgQ?rel=0" frameborder="0" allowfullscreen></iframe>

Object detection, pose estimation, segmentation (2019)

---

class: middle, center, black-slide

<iframe width="600" height="450" src="https://www.youtube.com/embed/8BFzu9m52sc?rel=0" frameborder="0" allowfullscreen></iframe>

Generating image descriptions (2015)

---

class: middle, center, black-slide

<iframe width="600" height="450" src="https://www.youtube.com/embed/IvmLEq9piJ4?rel=0" frameborder="0" allowfullscreen></iframe>

Detecting skin cancer (2017)

---

class: middle, center, black-slide

<iframe width="600" height="450" src="https://www.youtube.com/embed/egJ0PTKQp4U?start=223&rel=0" frameborder="0" allowfullscreen></iframe>

Compose music (NVIDIA, 2017)

---

# What is missing?

Intelligence is not just about **pattern recognition**, which is something most of these works are based on.

It is about *modeling the world*:
- explaining and understanding what we see;
- imagining things we could see but haven't yet;
- problem solving and planning actions to make these things real;
- building new models as we learn more about the world.

---
class: middle
# AI biases
## Who do you think will mostly likely commit a crime?
.center[

.width-40[![](https://static.propublica.org/projects/algorithmic-bias/assets/img/generated/Vernon-Prater-mugshot2-270*360-e39237.jpg)]&nbsp;&nbsp;&nbsp;
.width-40[![](https://static.propublica.org/projects/algorithmic-bias/assets/img/generated/Brisha-Borden-mugshot2-270*360-a06698.jpg)]
]
.footnote[Image credits: [ProPublica](https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing/)]
---

class: middle
# AI biases
## *Our present racial biases are being coded into the technology of the future :(*
.center[
.width-60[![](https://amueller.github.io/ml-workshop-1-of-4/slides/images/propublica_compas.png)]
]
.footnote[Image credits: [ProPublica](https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing/)]
---
class: middle
# AI biases
## > Twitter's Photo Cropping Algorithm Draws Heat for Possible Racial Bias
.center.width-100[![](https://petapixel.com/assets/uploads/2020/09/comparison_feat.jpg)]
---
class: middle
# AI biases
## > Israel Arrests Palestinian Because Facebook Translated 'Good Morning' to 'Attack Them'
.center.width-100[![](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQj-ZP_1DWT-8TsEQytJckDR3iBoWNxvLDlmw&usqp=CAU)]
---
class: middle
# AI biases
## > Only white babies appear in a search for "babies" on Microsoft search engine Bing.
.center.width-100[![](https://ichef.bbci.co.uk/news/976/cpsprodpb/35D4/production/_95508731_mediaitem95508730.jpg)]
---
class: middle
# AI biases
## > Google Mistakenly Tags Black People as ‘Gorillas.’
.center.width-100[![](https://ichef.bbci.co.uk/news/976/cpsprodpb/BC13/production/_83974184_29ba8607-9446-4298-9d9e-d33514811487.jpg)]
---
class: middle
# AI biases
## > Joy Buolamwini found her computer system recognised the white mask, but not her face.

.center[

.width-65[![](https://ichef.bbci.co.uk/news/976/cpsprodpb/136C8/production/_95506597_mediaitem95506596.jpg)]&nbsp;&nbsp;&nbsp;
.width-25[![](https://www.bu.edu/law/files/2019/04/joy-buolamwini-gender-shades.jpg)]
]
---

class: middle
# AI biases
## Why is this happening?
.center.width-90[![](https://theaisummit.com/wp-content/uploads/2018/09/IMG_3609-1024x683.jpg)]
.footnote[Image credits: [The AI Summit](https://theaisummit.com/)]

---
class: middle
# AI biases
## What is the solution?
### Diversity, equity, and inclusion: "AI lacks intelligence without different voices"
.center.width-100[![](https://pbs.twimg.com/media/DXyTjbKXcAATwSX.jpg)]

---

class: end-slide, center
count: false

The end.

---

# References

- Turing, Alan M. "Computing machinery and intelligence." Mind 59.236 (1950): 433-460.
- Newell, Allen, and Herbert Simon. "The logic theory machine--A complex information processing system." IRE Transactions on information theory 2.3 (1956): 61-79.
- Chomsky, Noam. "Rules and representations." Behavioral and brain sciences 3.1 (1980): 1-15.
