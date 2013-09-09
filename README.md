ethnicityguesser
================

DEPENDENCIES:
nltk

------------------------------------------------------------------------

CURRENT ETHNICITIES:
chinese
czech
danish
french
indian
japanese
jewish
spanish

------------------------------------------------------------------------

DOCUMENTATION:

Usage:

-- From the Python interpreter:

FROM SCRATCH:

Instantiation:

>>> from runner import make_classifier
>>> mxec = make_classifier()

Training: (note that make_classifier already passes in training tokens)

>>> mxec.train()

Classification: (After training)
>>> mxec.classify('leventhal')
'jewish'
>>> mxec.classify('sekhri')
'indian'

FROM PICKLE:

Instantiation:

>>> import cPickle as pickle
>>> pickle_file = open('pickled_classifiers/<insert pickle file here, e.g jewishandindian.pkl', 'rb')
>>> mxec = pickle.load(pickle_file)
>>> pickle_file.close()

Training: Done for you

Classification:
>>> mxec.classify('leventhal')
'jewish'
>>> mxec.classify('sekhri')
'indian'


-- In other code (as in a bigger project, etc):

from NLTKMaxentEthnicityClassifier import NLTKMaxentEthnicityClassifier as mxec
classifier = mxec(tokens) ## tokens must be a list of ([list of names], 'ethnicity') pairs. Ethnicities can be repeated.

Training and Classification as above.

------------------------------------------------------------------------

pickled_classifiers directory is full of pickled ([list of names], 'ethnicity') pairs

pickled_classifiers is full of pickled trained classifiers