# ASD Factors ML
## Autism Spectrum Disorder
Autism Spectrum Disorder (ASD) is a developmental disability that affects how a person experiences the world. Autism affects the way a person thinks, communicates, and socializes. It's important to note that these differences do not indicate that something is wrong with the person and autism is not something to be cured. Autism is a part of who a person is, and treatment for it is about learning how to live with the disorder in a neurotypical world, not about removing or changing aspects of who the person is is. For more information about autism, refer to [this page on the Autistic Self Advocacy Network website.](https://autisticadvocacy.org/about-asan/about-autism/)

## Not A Diagnostic Tool
We've made a few models that predict whether a child is diagnosed with ASD or not. These models are useful primarily to extract feature importance from, and not as actual predictors.  
**None of our models can be used for diagnosis, and if you think you have a disorder, then you should speak with a mental health professional about it.**

## Our Goal
Our goal is to analyze factors that may indicate someone is autistic in order to encourage people who think they (or their child) may be autistic to get diagnosed. Diagnosis can be an important step for improving quality of life in autistic people; once a person knows they're autistic and what that looks like for them, it allows them to learn coping strategies in order to better navigate the neurotypical world that we live in.  
To reiterate, **our goal is not to diagnose anyone.** Rather, we wish to encourage those who think they might be autistic to seek diagnosis.

## Who Cares?
Groups such as the [Autistic Self Advocacy Network](https://autisticadvocacy.org/about-asan/) work to empower autistic people to control their own lives. An important step toward that goal is for people to be educated about ASD, and diagnosed if they think they are autistic.  
We're going to look at factors that could indicate someone is autistic as a means to encourage people to educate themselves about autism.

## The Data
Data about ASD can be difficult to find, so we're using the topical data from the [National Survey of Children's Health](https://www.census.gov/programs-surveys/nsch/data/datasets.html) for the year of 2020. This data has a few limitations, but will work for our purpose. The main limitations are:
- The data is only collected about children. This a problem that pervades a lot of research about autism; it's often only studied in children despite the fact that autistic children grow up into autistic adults.
- The portion of children diagnosed with autism is small, which means we need to address this class imbalance in our modeling.
- The variables related to autism rely on a diagnosis from a medical professional. This is a limitation because autism often goes undiagnosed, and some people realize they or their child are autistic and choose not to get diagnosed for various reasons. This limitation is less significant than the others.

# Methods
**Considerations:**
- Since our goal is interpretation, we'll want to tend toward interpretable models.
- Since ASD is uncommon, we'll need to account for the class imbalance. This means not using accuracy as a primary metric; since a model that guesses nobody is autistic has a 97% accuracy.
- False positives are unreliable as it's impossible to know what portion of them are undiagnosed autistic children. This means precision isn't a very useful metric on its own (though shouldn't be ignored either).
- Recall is likely to be our most reliable metric, since we want to minimize false negatives to see what features our models find important.

