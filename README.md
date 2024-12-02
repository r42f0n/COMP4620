java cCOMP4620/8620: Advanced Topics in ML – Intelligent Robotics

Semester-22024–Assignment1

Duedate: Monday,26August202410.00amCanberratime

Graceperiod: 5hoursaftertheduedate

Latesubmission: Notpermitted

Pleasereadthefollowingnotesfirstbeforestartingtoworkontheassignment.

1. Thisisanindividualassignment.

2. Themaximumtotalmarkforthisassignmentis100points

3. This assignment consists of two parts: Part A and Part B. Part A contains conceptual questions

only. The maximum total mark for Part A is 30 points. Part B contains conceptual questions,

programmingandanalysis. ThemaximumtotalmarkforPartBis70points.

4. SubmissionInstruction:

(a) Youcanwriteyourprograminaprogramminglanguageofyourchoice.

(b) You must submit all of your source codes. If your program consists of multiple files,

you must place all files under a single folder, compress the folder into a single file with

one of the following extensions: .zip or .7z or .tar.gz, and submit this compressed file. If

your program consists of multiple files in multiple folders, your compressed file should

preservethefolderstructure.

(c) In your selection of programming language and in compressing the files, you must con-

sider that during the demo, you will need to download your submission, extract your

source codes, compile (if needed), and run the program in front of the tutor marking your

assignmentwithoutmakinganychangestothesourcecode.

(d) Allnon-programmingpartsoftheassignmentmustbewritteninasingle.pdffile.

(e) Thetwofiles(sourcecodesand.pdf)mustbesubmittedviawattlebeforetheduedate.

(f) Late submission is NOT permitted. However, we provide a 5 hours grace period. Within

the grace period, you can still submit your assignment. However, after the grace period

ends,youwillNOTbeabletosubmityourassignment.

5. Informationaboutthein-persondemowillbeannouncedintheclassforum.

PARTA

The questions in this part aim to explore the relation between

distanceintheC-spaceandintheworkspace.

To achieve the above objective, consider a planar kinematic

chain robot as illustrated in Figure 1. It has a static base, K ro-

tational joints and K links. Each joint is represented as a point.

Each link is a straight line segment with length L. It has two

end-points, called the origin and the extremity points. The po-

sition of the origin of the first link is fixed. The origin of the ith

linkfori ∈ [2,K]coincideswiththeextremityofthe(i?1)thlink Figure1: Anillustrationoftheplanar

atajointpoint. Therobotoperatesina2Dworkspacepopulated kinematicchainrobot.

byasetofobstaclesObs.

Page1of3–AdvancedTopicsinML:IntelligentRobotics–COMP4680/8650

Aconfigurationoftheaboverobotcanberepresentedbyq = (θ ,θ ,··· ,θ ),whereθ ∈ [0,2π)isthe

1 2 K i

jointanglethatdefinestheangle(inradian)betweenthebaseandthefirstlinkfori = 1,andbetween

theith and(i?1)th linkfori = [2,K]. TheC-spaceofthisrobotcanberepresentedasthespaceRK.

In addition, let us define the C-space distance between two configurations, q = (θ ,θ ,··· ,θ ) and

1 2 K

q(cid:48) = (θ(cid:48),θ(cid:48),··· ,θ(cid:48) ), as: d (q,q(cid:48)) = max |θ ? θ(cid:48)|. This distance metric is often used in motion

1 2 K C 1≤i≤K i i

planningbecauseitisfastertocompute,comparedtothetypicalEuclideandistance.

Pleaseanswerthefollowingquestions.

1. [20 pts] Given 2 configurations, q = (θ ,θ ,··· ,θ ) and q(cid:48) = (θ(cid:48),θ(cid:48),··· ,θ(cid:48) ), let us assume

1 2 K 1 2 K

the robot moves from q to q(cid:48) along a straight line segment qq(cid:48) in the C-space. It is known that

during such a movement, all points on the robot traces a path of length less than or equal to

α·d (q,q(cid:48)), where α is a constant that can be upper bounded in terms of the link length L and

C

thenumberoflinksK. PleasefindthisupperboundofαandexpressedtheminLandK. Please

provideitsderivation. Hintsareavailableinthelastpage.

2. [10 pts] Now, recall that the workspace distance d (q,Obs) between the configuration q and

W

obstacles Obs in the workspace is defined as the distance between the closest pair of points

on the robot placed at configuration q and Obs. Please find the radius τ of the neighbourhood

Neigh(q) = {q(cid:48) | d (q,q(cid:48)) ≤ τ} that will guarantee the robot can move from configuration q to

C

q(cid:48) (for any q(cid:48) ∈ Neigh(q)) collision-free, following a straight line path qq(cid:48). Please express τ in

termsoftheupperboundαfromA.1. andd (q,Obs).

W

PARTB

The questionsin this part aimto provide hands-onexperience and better understandingof Sampling-

based Motion Planning. To this end, let’s consider K rigid-body sphere robots are navigating a 3D

workspace[?50,50]×[?50,50]×[?50,50] ? R3 populatedbyobstaclesintheshapeofcubes. And

supposeeachrobotcanonlytranslate. Pleaseanswerthe代 写COMP4620、Java/Python
代做程序编程语言questionsbelow.

1. [5 pts] Please specify the C-space of the K robots. Assume that the origin of the coordinate

systemofeachrobotisatthecenterofthesphere.

2. [35 pts] Please write a sampling-based motion planning program for centralised planning of

the robots. A collision-free path here means the robot will not collide with the obstacles and

otherrobots. PleaseimplementeitherPRMwithanyoneormoresamplingstrategiesdiscussed

in class, EST, or RRT. You can use and extend the collision check methods discussed in the

pasttwoweekstutorials. Notethatanedgeinagraph/treeinSampling-basedMotionPlanning

represents a straight line-segment in the C-space, which in this case represents K (sub-)paths

for K robots. Weassumeallrobotsmoveinsuchawaythattheyspendtheexactsameduration

and use constant velocity to traverse their respective (sub-)paths, though the velocity used by

differentrobotsmaydiffer.

Theinputtoyourprogrammustbeatext(.txt)fileandfollowstheformatbelow.

(a) The file consists of K +|Obs|+2 lines, where K is the number of robots and |Obs| is the

numberofobstaclesintheenvironment.

(b) Thefirstlinecontainstwonumbersseparatedbyasinglewhitespace. Thefirstnumberin

thislineisthenumberofrobots,whilstthesecondnumberisthenumberofobstacles.

(c) The second line consists of K numbers, each separated by a white space. The ith number

inthislineistheradiusofrobot-i.

Page2of3–AdvancedTopicsinML:IntelligentRobotics–COMP4680/8650

(d) Each of line-3 to line K +2 contains 6 numbers, which specifies the initial and goal con-

figurationsoftheith robot,wherei = lineNumber?2. Theformatofeachlineis:

InitialConf X InitialConf Y InitialConf Z ; GoalConf X GoalConf Y GoalConf Z

(e) Each of line K +3 to line K +|Obs|+2 contains 4 numbers separated by a white space,

which specifies the position of the center point and side length of the jth obstacle where

j = lineNumber?(K +2)Theformatofeachoftheselinesis:

CenterPt X CenterPt Y CenterPt Z SideLength

The output to your program must be a text (.txt) file that specifies the collision-free path (a

sequence of line segments) for the robots to move from the given initial to goal configurations.

Theformatoftheoutputfileisasfollows.

(a) Thefileconsistsofn+2lines,wherenisthenumberoflinesegmentsinyourpath

(b) Thefirstlineisthenumberofline-segments

(c) The second line consists of 3K numbers, specifying the initial configuration of each of

the K robots. Each configuration is separated by a semicolon, while each number in a

configurationisseparatedbyawhitespace. Specifically,theformatofline-2is:

ConfRobot-1 X ConfRobot-1 Y ConfRobot-1 Z ; ConfRobot-2 X ConfRobot-2 Y

ConfRobot-2 Z ; ··· ; ConfRobot-K X ConfRobot-K Y ConfRobot-K Z

(d) Thenextnlinesaretheendconfigurationofeachlinesegment. Eachoftheselinesconsists

of3K numbersandusestheformatasspecifiedforline-2oftheoutputfile(aboveitem)

During demonstration, we will test the correctness of your program. For this purpose, we will

providethreeproblemsandgiveyourprogramupto1minutetosolveeachproblem.

3. [12 pts] Please evaluate the required time that your program needs to solve queries (i.e., find

collision free paths) as the number of robots increases. For this purpose, please run your pro-

gram for K = {1,3,5,7} on the same environment of your design. For each value of K, you

should run for at least 10× to gather the average and 95%-confidence interval of the time to

solvequeries. Ifthetimetofindthesolutionistoolong,youcanputalimitontherun-timeand

recordthesuccessrateofsolvingquerieswithinthegiventime,inadditiontothetimetosolve

queries. Please explain your selection of the environment, compare the results for the different

K andexplainyourfindings.

4. [12 pts] Please evaluate the performance of your program as the problem becomes more com-

plex. To this end, please use K = 3 but alter the testing environment systematically, so as to

tease out the complexity of sampling-based motion planning (hint: the concept of (cid:15),α,β could

be useful in this design). For each environment, you should run for at least 10× to gather the

averageand95%-confidenceintervalofthetimetosolvequeries. Ifthetimetofindthesolution

is too long, you can put a limit on the run-time and record the success rate of solving queries

within the given time, in addition to the time to solve queries. Please explain your selection of

theenvironments,comparetheresultsforthedifferentenvironment,andexplainyourfindings.

5. [6pts]WhatdoyouthinkcanbedonetoimprovetheperformanceyougetinB.3andB.4?

oOo That’s all folks oOo

)1+2

K(K =

i1= Ki

(cid:80) ?

r·θsinaidar θelgnalartnecdna rsuidarhtiwelcricafocranA ?

.1.ArewsnaotsalumrofgniwollofehtdeenylekillliwuoY :tniH

Page3of3–AdvancedTopicsinML:IntelligentRobotics–COMP4680/8650

         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
