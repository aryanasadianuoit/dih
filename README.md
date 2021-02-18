# Distilling Knowledge via Intermediate Classifier Heads (DIH)
<section>
<p text-align: justify>
  <b>Distilling Knowledge via Intermediate Classifier Heads (DIH)</b> is a knowledge distillation framework which specifically tries to mitigate the negative impact of <b>capacity gap</b> between the teacher and the student model on knowledge distillation.
<br>
  This approach improves the canonical knowledge distillation (KD) with the help of teacher's <b>intermediate representations</b>.
  <br>
  DIH pipeline:
  <ol>
  <li>First <b>k</b> classifier heads have to be mounted at various intermediate layers of the tecaher.</li>
  <li>The added intermediate classifier heads pass a <b>cheap</b> fine-tuning ( while the main teacher is forzen).</li>
  <li>The cohort of classifiers (all the mounted ones + the final main classifier) co-teach the student simultaneously with knowledge distillation.</li>
  </ol>
  <br>
Our experiments on various teacher-student pairs of models and datasets have demonstrated that the proposed approach outperforms the canonical knowledge distillation approach and its extensions, which are intended to address the capacity gap problem.
  </p>
  <br>
    <img src="DIH.png" alt="Distilling Knowledge via Intermediate Classifier Heads (DIH)"width: 60% height: 60% justify-content: center>

  </section>
  
  
  
  <section>
  <h2>Requirements</h2>
  <ul>
  <li>torch==1.7.1</li>
  <li>torchvision==0.8.2</li>
  <li>tqdm==4.48.2</li>
  <li>torchsummary</li>
   <li>numpy==1.19.4</li>
 </ul>
  <code>pip install -r requirements.txt</code>
</section>
  
  <section>
  <h2>Baseline</h2>
  <p>Student=ResNet8, Teacher=ResNet110, CIFAR-100  </p>
  <code>python3 test_dih.py --alpha 0.1  --batch_size 64  --dataset cifar100  --epochs 200 --gpu_id 0  --lr 0.1 --schedule [60, 120, 180] --temperature 5 --wd 0 .0005
</code>
  

  
</section>
