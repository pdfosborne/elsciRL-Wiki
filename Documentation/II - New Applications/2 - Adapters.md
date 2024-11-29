Table of Contents

- [Adapter Selection](<#adapter-selection>)
- [Custom Adapters](<#custom-adapters>)
	- [Editing the Encoder](<#editing-the-encoder>)
	- [Transforming States](<#transforming-states>)
- [Applying Neural Agent to Language Adapter](<#applying-neural-agent-to-language-adapter>)

---
# Adapter Basics

Adapters specify any transformations to the naturally defined state from the data engine. Crucially, this includes encoding it into a numeric form that enables agent's to act on.

These follow the form... TODO

# Adapter Selection

From the template configuration you may be curious as to what the differences between adapter choices is. In short, this is the selection that allows us to define how each state should be encoded (transformed into a vector to input into the agent).

It just happens that the *Default* adapter from the template specifies an encoder for a 4x4 grid that matches the current Frozen Lake environment. Therefore ***NO CHANGES ARE NEEDED*** for this example.

If we chose instead to use the 8x8 Gym generation we would need to update line 19 in the image below to match this.

In theory, a tabular agent does not need to use an encoder at all and could instead simply store the natural format of the state. However, this can be computationally expensive if they are strings (text) and is good practice to use an encoder to enable neural methods to also be used.

![Adapter Example](<./attachments/Adapter Example.png>)

---

# Custom Adapters

## Editing the Encoder

Adapters are problem specific and is why they are included in the application template and not fixed in the elsciRL library. They must provide a problem specific method for transforming the raw state defined by the data engine into a numeric form that the agent's can understand. 

In this same Frozen Lake example, we have another environment setup for an 8x8 grid and therefore we duplicate the default adapter with a single change in line 19. We also give the file a relevant name.

![Editing the Encoder](<./attachments/Editing the Encoder.png>)

Then this new adapter must be included as an input option in the experiment before it will be usable in the configuration.

TODO - SHOW IMAGE OF ADAPTERS DICT FOR INPUT

We can then call the *Default_8x8* adapter and run the experiment again. Without any other changes it performs just as bad as it did on the 4x4 grid which is not surprising with so few episodes.

![FrozenLake\_8x8 Run](<./attachments/FrozenLake_8x8 Run.png>)

![FrozenLake\_8x8 Results](<./attachments/FrozenLake_8x8 Results.png>)

## Transforming States

Although the primary usage of the adapter is to define an encoder, it can also be used to specify a transformation process. In short, a set of rules can be used to map any observed state to a new form.

In this example, we can re-define the original environment as a Text Game. To do this, we will be updating the language adapter to the following.

In this case we have defined a simple lookup to map any of the 16 possible states in the 4x4 problem to a language term.

The encoder that is set by the template is a sentence transformer and is suitable for now.

![Language Adapter](<./attachments/Language Adapter.png>)

We then simply change the engine generation back to the 4x4 Gym problem and update the configs to now train a tabular agent on both the default numeric form and the new language one.

![Language Adapter Config](<./attachments/Language Adapter Config.png>)

The output of this experiment will combine the results for both adapters into a single summary figure.

![Language Adapter Output](<./attachments/Language Adapter Output.png>)

# Applying Neural Agent to Language Adapter

The previous results show a tabular agent treats each state as unique and has very limited mechanisms to transfer knowledge of similar states. Neural agent are far more favoured in recent works and so we can apply them now.

Previously when we tried to run the neural agent as it was set in the template an error occurred.

TODO