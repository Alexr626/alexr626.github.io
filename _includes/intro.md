I'm a Machine Learning Engineer at [Nokia](https://www.nokia.com/), and I'm applying to PhD programs for Fall 2027. I completed my M.S. in Computer Science at the [University of Southern California](https://www.usc.edu/) in 2026, and before that my B.Sc. in Computer Science and Statistics at the [University of British Columbia](https://www.ubc.ca/). Along the way I've worked on ML research and engineering at Nokia Bell Labs and Medtronic.

**My research uses mechanistic interpretability to understand how vision-language models integrate what they see with what they read, and where that integration goes wrong.** Many of the failures I find most interesting only exist at the intersection of modalities. In [compositional safety failures](https://arxiv.org/abs/2610.07514), for example, an image and a prompt that are each benign combine into an unsafe output, and the model's judgment depends on how visual evidence is routed into its language representations. I study these interactions with causal methods, such as causal tracing, activation patching and counterfactual interventions, to localize *where* and *in which components* cross-modal information shapes a model's behavior. Ultimately, I want this understanding to support principled inference-time interventions, such as activation steering, that make VLMs safer and less prone to hallucination without retraining.

<details class="questions" markdown="1">
<summary>Questions I'm thinking about (late 2026)</summary>

- Do VLMs build genuinely shared multimodal representations, or does visual information stay a separable "add-on" to the language model's residual stream?
- At which layers and components does visual evidence start to change a model's safety or factuality judgment, and how stable is this across model families?
- How can we tell whether a benchmark is measuring cross-modal reasoning rather than text-only shortcuts?
- Longer term: can interpretability tools developed for language models carry over to self-supervised, joint-embedding (JEPA-style) world models, whose representations aren't tied to tokens at all?

</details>

I came to interpretability through causal inference. At UBC, I worked on causal ML for clinical treatment-effect estimation. Later, I led [a project](https://arxiv.org/abs/2503.19394) using CausaLM-style counterfactual representations to measure how individual symptoms causally drive a language model's diagnoses. Both left me more interested in *why* models make the predictions they do than in the predictions themselves, and that question has carried into my work on vision-language models.
