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


## WEEK 3 
I learned to use Zotero this week. Its plugin can automatically generate the bibliography from the website and save to the local folder. This activity will be helpful for the future paper.

##### Reading List
Ahmad, M., Bani Mohammad, E., & Anshasi, H. A. (2020). Virtual Reality Technology for Pain and Anxiety Management among Patients with Cancer: A Systematic Review. Pain Management Nursing. https://doi.org/10.1016/j.pmn.2020.04.002

Baños, R. M., Espinoza, M., García-Palacios, A., Cervera, J. M., Esquerdo, G., Barrajón, E., & Botella, C. (2013). A positive psychological intervention using virtual reality for patients with advanced cancer in a hospital setting: A pilot study to assess feasibility. Supportive Care in Cancer: Official Journal of the Multinational Association of Supportive Care in Cancer, 21(1), 263–270. https://doi.org/10.1007/s00520-012-1520-x

Bolt, R. A. (1980). “Put-that-there”: Voice and gesture at the graphics interface. Proceedings of the 7th Annual Conference on Computer Graphics and Interactive Techniques  - SIGGRAPH ’80, 262–270. https://doi.org/10.1145/800250.807503

Carfagno, J. (2019, May 6). How Osso VR is Reshaping the Surgical Training Process. Docwire News, Retrieved from https://www.docwirenews.com/docwire-pick/future-of-medicine-picks/how-osso-vr-is-reshaping-the-surgical-training-process/

Chirico, A., Lucidi, F., De Laurentiis, M., Milanese, C., Napoli, A., & Giordano, A. (2016). Virtual Reality in Health System: Beyond Entertainment. A Mini-Review on the Efficacy of VR During Cancer Treatment. Journal of cellular physiology, 231(2), 275–287. https://doi.org/10.1002/jcp.25117

Clay, F., Howett, D., FitzGerald, J., Fletcher, P., Chan, D., & Price, A. (2020). Use of Immersive Virtual Reality in the Assessment and Treatment of Alzheimer’s Disease: A Systematic Review. Journal of Alzheimer’s Disease: JAD, 75(1), 23–43. https://doi.org/10.3233/JAD-191218

Crochet, P., Aggarwal, R., Dubb, S. S., Ziprin, P., Rajaretnam, N., Grantcharov, T., Ericsson, K. A., & Darzi, A. (2011). Deliberate practice on a virtual reality laparoscopic simulator enhances the quality of surgical technical skills. Annals of Surgery, 253(6), 1216–1222. https://doi.org/10.1097/SLA.0b013e3182197016

Dascal, J., Reid, M., IsHak, W. W., Spiegel, B., Recacho, J., Rosen, B., & Danovitch, I. (2017). Virtual Reality and Medical Inpatients: A Systematic Review of Randomized, Controlled Trials. Innovations in Clinical Neuroscience, 14(1–2), 14–21.

de Almeida Souza, I., Sanches, C., Kondo, M. N. S., & Zuffo, M. K. (2008). Development and evaluation of a virtual reality simulator for training of thyroid gland nodules needle biopsy. Proceedings of the 2008 ACM Symposium on Virtual Reality Software and Technology, 245–246. https://doi.org/10.1145/1450579.1450635

de Lima, L., Nunes, F. L. S., Takashi, R., Rodello, I., Brega, J. R. F., & Sementille, A. C. (2004). Virtual reality for medical training: A prototype to simulate breast aspiration exam. Proceedings of the 2004 ACM SIGGRAPH International Conference on Virtual Reality Continuum and Its Applications in Industry, 328–331. https://doi.org/10.1145/1044588.1044659

Engelbart, D. C., & English, W. K. (1968). A research center for augmenting human intellect. Proceedings of the December 9-11, 1968, Fall Joint Computer Conference, Part I on - AFIPS ’68 (Fall, Part I), 395. https://doi.org/10.1145/1476589.1476645

Foreman, K. B., Wilson, C., Dibble, L. E., & Merryweather, A. S. (2019). Training Persons with Parkinson Disease using an Advanced CAVE Virtual Reality System. The FASEB Journal, 33(S1), 335.4-335.4. https://doi.org/10.1096/fasebj.2019.33.1_supplement.335.4

Gershon, J., Zimand, E., Pickering, M., Rothbaum, B. O., & Hodges, L. (2004). A pilot and feasibility study of virtual reality as a distraction for children with cancer. Journal of the American Academy of Child and Adolescent Psychiatry, 43(10), 1243–1249. https://doi.org/10.1097/01.chi.0000135621.23145.05

Harrington, C. M., Kavanagh, D. O., Quinlan, J. F., Ryan, D., Dicker, P., O’Keeffe, D., Traynor, O., & Tierney, S. (2018). Development and evaluation of a trauma decision-making simulator in Oculus virtual reality. The American Journal of Surgery, 215(1), 42–47. https://doi.org/10.1016/j.amjsurg.2017.02.011

Henriksen, B., Nielsen, R., Kraus, M., & Geng, B. (2017). A Virtual Reality System for Treatment of Phantom Limb Pain using Game Training and Tactile Feedback. Proceedings of the Virtual Reality International Conference - Laval Virtual 2017, 1–4. https://doi.org/10.1145/3110292.3110306

Hoffman, H. G., Patterson, D. R., Seibel, E., Soltani, M., Jewett-Leahy, L., & Sharar, S. R. (2008). Virtual reality pain control during burn wound debridement in the hydrotank. The Clinical Journal of Pain, 24(4), 299–304. https://doi.org/10.1097/AJP.0b013e318164d2cc

Krueger, M. W. (1977). Responsive environments. Proceedings of the June 13-16, 1977, National Computer Conference on - AFIPS ’77, 423. https://doi.org/10.1145/1499402.1499476

Li, A., Montaño, Z., Chen, V. J., & Gold, J. I. (2011). Virtual reality and pain management: Current trends and future directions. Pain Management, 1(2), 147–157. https://doi.org/10.2217/pmt.10.15

Luo, H., Cao, C., Zhong, J., Chen, J., & Cen, Y. (2019). Adjunctive virtual reality for procedural pain management of burn patients during dressing change or physical therapy: A systematic review and meta-analysis of randomized controlled trials. Wound Repair and Regeneration: Official Publication of the Wound Healing Society [and] the European Tissue Repair Society, 27(1), 90–101. https://doi.org/10.1111/wrr.1

Nilsson, S., Finnström, B., Kokinsky, E., & Enskär, K. (2009). The use of Virtual Reality for needle-related procedural pain and distress in children and adolescents in a paediatric oncology unit. European Journal of Oncology Nursing: The Official Journal of European Oncology Nursing Society, 13(2), 102–109. https://doi.org/10.1016/j.ejon.2009.01.003

Oyama, H., Aono, M., Ohbuchi, R., & Suda, S. (1995). VR Medical Support System for Cancer Patients - Cancer Edutainment VR Theater (CEVRT) and Psycho-Oncological VR Therapy (POVRT). Interactive Technology and the New Paradigm for Healthcare (Vol. 18, Studies in Health Technology and Informatics, pp. 433-438). doi:10.3233/978-1-60750-862-5-433

Satava, R. M., Morgan, K., & Sieburg, H. B. (1995). Interactive Technology and the New Paradigm for Healthcare. IOS Press.

Singh, P., Aggarwal, R., Tahir, M., Pucher, P. H., & Darzi, A. (2015). A randomized controlled study to evaluate the role of video-based coaching in training laparoscopic skills. Annals of Surgery, 261(5), 862–869. https://doi.org/10.1097/SLA.0000000000000857

Szczepańska-Gieracha, J., Cieślik, B., Rutkowski, S., Kiper, P., & Turolla, A. (2020). What can virtual reality offer to stroke patients? A narrative review of the literature. NeuroRehabilitation. https://doi.org/10.3233/NRE-203209

Varshney, R., Frenkiel, S., Nguyen, L. H., Young, M., Del Maestro, R., Zeitouni, A., Saad, E., Funnell, W. R. J., Tewfik, M. A., & National Research Council Canada. (2014). The McGill simulator for endoscopic sinus surgery (MSESS): A validation study. Journal of Otolaryngology - Head & Neck Surgery, 43(1), 40. https://doi.org/10.1186/s40463-014-0040-8

Vovk, A., Patel, A., & Chan, D. (2019). Augmented Reality for Early Alzheimer’s Disease Diagnosis. Extended Abstracts of the 2019 CHI Conference on Human Factors in Computing Systems, 1–6. https://doi.org/10.1145/3290607.3313007

Wolitzky, K., Fivush, R., Zimand, E., Hodges, L., & Rothbaum, B. O. (2005). Effectiveness of virtual reality distraction during a painful medical procedure in pediatric oncology patients. Psychology & Health, 20(6), 817–824. https://doi.org/10.1080/14768320500143339

Zengin, S., Kabul, S., Al, B., Sarcan, E., Doğan, M., & Yildirim, C. (2013). Effects of music therapy on pain and anxiety in patients undergoing port catheter placement procedure. Complementary Therapies in Medicine, 21(6), 689–696. https://doi.org/10.1016/j.ctim.2013.08.017

##### Suggested Readings
###### Perception of the future and the future of perception

Let there be vision and there was light.

Our rules and principles are based on past knowledge. If the future always depends on the past, then the world and society will be hard to change. The modern world teaches people to follow those rules, and most of us become obedient as we grew up. Crow enjoys being ruled by the dominator (what we called elite class), so people won't decide or think about the future. 

In the article, Heinz mentions the insignificance of former information and relevance for a new future. We have to perceive our tomorrow first so we can achieve it later. This made me think the language we are using could also be the stumbling block that prevents us from perceiving the future or reaching a higher dimension. But after that, what will our perception eventually be like at that moment?

###### Vehicles: Experiments in synthetic psychology

The article starts with a simple vehicle. This vehicle eventually becomes alive by adding more sensors and more motors when interacting with multiple stimuli. Using the threshold for any action value can simulate a delay of preparation or rest that usually happens in life entities. Binding multiple thresholds with one activation element will generate a more realistic life. Alghouth the idea is not too complicated but the result (performance) always looks intricate.

Most AI I made was in video games, I usally randomize their animations and directions to simulate the dynamic patrolling. It is interesting to discover this new vehicle algorithm by adding more relative sensors and motors with various settings to make the virtual world full of life.



## WEEK 4
    
For this week's assignment, I made a multi-sensors vehicle based on the in-class sketch. The vehicle prefers to avoid its companions but chase the light source. It is not easy to calculate all incoming forces in a javascript program compared to any other game engine. So I use velocities to generate the next position (sum up the same direction velocity, subtract different directions velocity). The script still has some problems that sometimes the vehicle won't be affected by the light source; even they are close enough. More details and features will be shared in class.    

<p class="codepen" data-height="383" data-theme-id="dark" data-default-tab="js,result" data-user="zian-liu" data-slug-hash="vYGoeZe" style="height: 383px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Vehicle">
  <span>See the Pen <a href="https://codepen.io/zian-liu/pen/vYGoeZe">
    </p>
<script async src="https://static.codepen.io/assets/embed/ei.js"></script>

    
