# HIVE: Evaluating the Human Interpretability of Visual Explanations


### [Project Page](https://princetonvisualai.github.io/HIVE/) | [Paper](https://arxiv.org/abs/2112.03184)

This repo provides the code for HIVE, a human evaluation framework for interpretability methods in computer vision.

```
@article{kim2021hive,
  author = {Sunnie S. Y. Kim and Nicole Meister and Vikram V. Ramaswamy and Ruth Fong and Olga Russakovsky},
  title = {{HIVE}: Evaluating the Human Interpretability of Visual Explanations},
  journal = {CoRR},
  volume = {abs/2112.03184},
  year = {2021}
}
```


## Our study UIs

#### Distinction task
- combined_gradcam_nolabels.html
- combined_bagnet_nolabels.html
- combined_protopnet_distinction.html
- combined_prototree_distinction.html

#### Agreement task
- combined_protopnet_agreement.html
- combined_prototree_agreement.html

#### Additional studies
- combined_gradcam_labels.html
- combined_bagnet_labels.html
- combined_prototree_agreement_tree.html



## Running human studies

We ran our studies through Human Intelligence Tasks (HITs) deployed on [Amazon Mechanical Turk](https://www.mturk.com/) (AMT).
We use [simple-amt](https://github.com/jcjohnson/simple-amt), a microframework for working with AMT. 
Here we describe which files correspond to which study UIs and provide brief instructions for running studies. 

### Brief instructions on how to run user studies on AMT

Please check out the original [simple-amt](https://github.com/jcjohnson/simple-amt) repository for more information on how to run a HIT on AMT.

#### Launch HITs on AMT
```
python launch_hits.py \
--html_template=hit_templates/combined_prototree_distinction.html \
--hit_properties_file=hit_properties/properties.json \
--input_json_file=examples/input_prototree_distinction.txt \
--hit_ids_file=examples/hit_ids_prototree_distinction.txt --prod
```

#### Check HIT progress
```
python show_hit_progress.py \
--hit_ids_file=examples/hit_ids_prototree_distinction.txt --prod
```

#### Get results
```
python get_results.py \
  --hit_ids_file=examples/hit_ids_prototree_distinction.txt \
  --output_file=examples/results_prototree_distinction.txt \
  > examples/results_prototree_distinction.txt --prod
```

#### Approve work
```
python approve_hits.py \
--hit_ids_file=examples/hit_ids_prototree_distinction.txt --prod
```
