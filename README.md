## WEEK 2

###### Here is my first sketch study
<p class="codepen" data-height="446" data-theme-id="dark" data-default-tab="js,result" data-user="zian-liu" data-slug-hash="OJNEXKg" data-preview="true" style="height: 446px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="5010 AS1">
  <span>See the Pen <a href="https://codepen.io/zian-liu/pen/OJNEXKg">
  5010 AS1</a> by Zian Liu (<a href="https://codepen.io/zian-liu">@zian-liu</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>


For my first sketch, I have added a few bouncing effects. First of all, after detecting the collision event (the new point is out of canvas), the future points will all be calculated to a reverse direction by using `math.abs()` until the next collision. When the bouncing happens, I also add a little variant to the line's each point's position, so you will see the line begins to vibrate. What is more, to make the animation become more attractive, the line can switch to various colors by touching different edges. This animation is like a dynamic screensaver, but out of fashion, like from the 90s.

I haven't used javascript for over three years. The most time I spent on this sketch is to figure out how to use its array correctly. When I was debugging the yellowtail scripts that Graham provides to us, I found the marks array not only includes a few pair s of dx, dy value, but also the mouse initial x, y position, and then a boolean. After a little meditation and researching, I realized the same array in javascript is capable to include different types like numbers, booleans, and strings together. However, most js tutorial websites neither mention that nor give a proper example.

<img src=" https://lh3.googleusercontent.com/yp-OYLpTngMAE6mdo2MOg6gBgHuG1PmJC7zxTXOE35OMG07Nz4GlftVBvoOqdwL71IQnZXyin955_i6yFLYfKKISKAZKgv4FPN6J3qoF39rqtKoVqUGNBaLvaEvuEl0UW0WXSqRYpwVHolyp1J57JotUIiV7wK0SqrpVF8i0M3tMkPttTWj7hNdjvBPFY32t6V4T5OY2B0qKL-23Q8k1wPkT8bshmmiLRM4zx3SIkkwtygAZmqG92HyQN4QY2sgSsvyPIf9EayAtIayI7tjAcxy7jNfJGfOACx1sFyuklLiE6dFTHLbdUzFYqSWXEHDjgZpRVog0es-kW-f3pPz_mgj9dLIcvc4LLt8IxzCe4uY48LqSMH8_tUO-FXYIr2_vQ8eMgL9IReVP-92fH6JvcFj96ctZwddBE7H_vUqoGz2Q5GoF7v0KFCpRDDtOKySS2NurJhNNYKnPrFN1P7b74eauvbXcURYNntL4GNz0doHfWhNl3ThULSenYRLgdWW7PVcqFWKWftidCrhmAxcILdM9IsyrDmtBS2oDw8oD6_i9WH8TlO9MKnww8A6Wk9OAtzRZsDmsTSPESvMOTo-hAdfWM6gkbedvZzxWVNoKhHadWeTGmLgtDAaiuf5g8NupYzRVFou3l1zfjGkuzndTd1hTYzW4mWZv3Gwnu10HgNsbQic6IiqLRj7u4G38Wg=w431-h214-no?authuser=0" width="300">

An issue I'm thinking for the whole week is to achieve perfect symmetry after relection. If I draw a specific pattern in the panel, after reflecting from the edge, neither the yellowtail script nor my codes can make the line remain the same as before ---- the pattern usually becomes an irregular curve after the bouncing.



<img src="https://lh3.googleusercontent.com/pw/ACtC-3d6G_Tevzi12wrrPobva75ibK50ck8V9aGKRObVyzTrQ39CYxHZ3xsOpRx2tL9iQzIeM8hdR8_Ap1CaIGdNEJ9L_w2V-fJVAW17qaWbflhN9VcJXoZyDFSmrZufCKnz9ODfB23507lgx5eDdksH7827=w988-h969-no?authuser=0" width="200">

The script below is my initial thinking about this problem. Once the new point is out of the edge, the next vector should be exactly the last vector that brought the line to reach the edge but in a different direction. The vector after next should be the vector before last but in a different direction. 

For the array, each time I should pop the tail to return the previous vector, calculate and unshift the new point to the beginning of the array so the previous vectors will be retrieved from back to end one by one. Maybe?
Unfortunately, my script doesn't work well, but I think this concept is worth sharing.

```javascript
       //TO achieve a perfect sysmetry,

        
        first = mark.pop();
        //return current (last) point and remove it
        second = mark[mark.length - 2];
        //return the point before last point

        var newP;
        // create newpoint 

        dx = second.x - first.x;
        dy = second.y - first.y;
        //calculate the last vector from the end of array

        newP.x = first.x + dx;
        newP.y = first.y - dy;        
        //rotate the direction and assign to new point 

        mark.unshift(newP);
```


### Literature Review Part 1
Use Immersive virtual reality to help COVID-19 patients or healthcare workers.

The situation of immersive Virtual Reality in the medical field is similar to the game industry -- slow and nonsignificant. A majority of applications are about reducing pain (entertainment nature) and surgery simulation (most are simple softwares made by unity and maya3D, only a few are for commercial use e.g., OSSO VR)

Unlike vaccine worldwide competition, VR is silent these days(almost no research about covid-19).It doesn't keep pace with the epidemic.
#### My Direction (Maybe)
Easy: Repeat previous distraction experiments, using level design to improve the immersive experience for patients that have shortness of breath or difficulty breathing?

Difficult: Nucleic acid-based testing (PCR) simulation for the nurse? or further 


##### Collection of papers
'Put-That-There': Voice and Gesture at the Graphics Interface
Richard A. Bolt, 1980

A Research Center for Augmenting Human Intellect
Douglas Engelbart and William English, 1968

Responsive Environments
Myron Krueger, 1977

Two Selections by Brenda Laurel
The Six Elements and Causal Relations Among Them (from Computers as Theater), 1991
Star Raiders: Dramatic Interaction in a Small World, 1986

Virtual Reality in Health System: Beyond Entertainment. A Mini‐Review on the Efficacy of VR During Cancer Treatment
Andrea Chirico  Fabio Lucidi  Michele De Laurentiis  Carla Milanese  Alessandro Napoli  Antonio Giordano

Zengin S, Kabul S, Al B, Sarcan E, Doğan M, Yildirim C. 2013. Effects of music therapy on pain and anxiety in patients undergoing port catheter placement procedure. Complement Ther Med 21: 689– 696.

Wolitzky K, Fivush R, Zimand E, Hodges L, Rothbaum BO. 2005. Effectiveness of virtual reality distraction during a painful medical procedure in pediatric oncology patients. Psychol Health 20: 817– 824.

Varshney R, Frenkiel S, Nguyen LH, Young M, Del Maestro R, Zeitouni A, Tewfik MA. National Research Council Canada 2014. Development of the McGill simulator for endoscopic sinus surgery: A new high‐fidelity virtual reality simulator for endoscopic sinus surgery. Am J Rhinol Allergy 28: 330– 334.

Singh P, Aggarwal R, Tahir M, Pucher PH, Darzi A. 2014. A randomized controlled study to evaluate the role of video‐based coaching in training laparoscopic skills. Ann surg 261: 862– 869.

VR Medical Support System for Cancer Patients - Cancer Edutainment VR Theater (CEVRT) and Psycho-Oncological VR Therapy (POVRT)
Hiroshi Oyama, Tatsuo Miyazawa, Masaki Aono, Ryutarou Ohbuchi, Susumu Suda

Gershon J, Zimand E, Pickering M, Rothbaum BO, Hodges L. 2004. A pilot and feasibility study of virtual reality as a distraction for children with cancer. J Am Acad Child Adolesc Psychiatry 43: 1243– 1249.


Virtual Reality Pain Control During Burn Wound Debridement in the Hydrotank
Hoffman, Hunter G. PhD*; Patterson, David R. PhD†; Seibel, Eric PhD*; Soltani, Maryam MEd†; Jewett-Leahy, Laura BA†; Sharar, Sam R. MD

Muayyad Ahmad, Eslam Bani Mohammad, Huda A. Anshasi, Virtual Reality Technology for Pain and Anxiety Management among Patients with Cancer: A Systematic Review, Pain Management Nursing

Virtual Reality and Medical Inpatients: A Systematic Review of Randomized, Controlled Trials
Julieta Dascal, BA, Mark Reid, PhD, Waguih William IsHak, MD, FAPA, Brennan Spiegel, MD, FACG, Jennifer Recacho, MA, Bradley Rosen, MD, and Itai Danovitch, MD, MBAcorresponding author

A positive psychological intervention using virtual reality for patients with advanced cancer in a hospital setting: a pilot study to assess feasibility
Rosa M. Baños, Macarena Espinoza, Azucena García-Palacios, José M. Cervera, Gaspar Esquerdo, Enrique Barrajón & Cristina Botella 

Virtual reality and pain management: current trends and future directions
Angela Li, Zorash Montaño, Vincent J Chen & Jeffrey I 

The use of Virtual Reality for needle-related procedural pain and distress in children and adolescents in a paediatric oncology unit

Adjunctive virtual reality for procedural pain management of burn patients during dressing change or physical therapy: A systematic review and meta‐analysis of randomized controlled trials
Huaxiu Luo MD  Chang Cao PhD  Jian Zhong MD  Junjie Chen PhD  Ying Cen PhD

Joanna Szczepańska-Gieracha, Błażej Cieślik, Sebastian Rutkowski, Paweł Kiper, Andrea Turolla, What can virtual reality offer to stroke patients? A narrative review of the literature.

Deliberate Practice on a Virtual Reality Laparoscopic Simulator Enhances the Quality of Surgical Technical Skills
P. Crochet, R. Aggarwal, S. S. Dubb, P. Ziprin, N. Rajaretnam, T. Grantcharov, K. Ericsson, A. Darzi

Development and evaluation of a trauma decision-making simulator in Oculus virtual reality
Cuan M. Harringtona,*, Dara O. Kavanagha, John F. Quinlanb, Donncha Ryana,Patrick Dickerc, Dara O'Keeffea, Oscar Traynora, Sean Tierney

Training Persons with Parkinson Disease using an Advanced CAVE Virtual Reality System
K Bo Foreman  Christopher Wilson  Leland E Dibble  Andrew S Merryweather

Use of Immersive Virtual Reality in the Assessment and Treatment of Alzheimer’s Disease: A Systematic Review
Clay, Felixa; b; * | Howett, Davidc | FitzGerald, Jamesa; b | Fletcher, Paula; d; e | Chan, Dennisc; f | Price, Annabela; b


Augmented Reality for Early Alzheimer's Disease Diagnosis
Alla  Vovk , Ameera  Patel , Dennis  Chan 

 https://www.docwirenews.com/docwire-pick/future-of-medicine-picks/how-osso-vr-is-reshaping-the-surgical-training-process/

 
A Virtual Reality System for Treatment of Phantom Limb Pain using Game Training and Tactile Feedback
Bartal  Henriksen profile imageBartal Henriksen, Ronni  Nielsen profile imageRonni Nielsen, M. Kraus profile imageMartin Kraus, Bo  Geng profile imageBo Geng


Development and evaluation of a virtual reality simulator for training of thyroid gland nodules needle biopsy
Ilana  De Almeida Souza profile imageIlana de Almeida Souza, Claudiney  Sanches profile imageClaudiney Sanches, Marcia N S Kondo profile imageMarcia N. S. Kondo, Marcelo Knörich Zuffo profile imageMarcelo Knorich Zuffo

Virtual reality for medical training: a prototype to simulate breast aspiration exam

#### Some keywords from research
Expense, no softwares

psychological wellbeing 

pediatric oncology

distraction, Managing Pain and Anxiety

Cancer-Related Symptom Management,

Mental Health Treatment

neuropathic pain

deliberate practice,laparoscopic cholecystectomy

Alzheimer's disease，spatial memory loss --- navigation task， store retrieve in place/object

OSSO VR - orthopedic surgery

Plan Surgeries

explain complex condition and treatment option

aspiration examination for breast cancer

virtual hands for Phantom Limb Pain

