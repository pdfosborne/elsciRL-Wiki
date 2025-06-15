### Adapters
Adapters unify problems into a standard form so any agent in the elsciRL library can be used.

In short, it transforms the state to a new form, optionally adding more context and then outputting a tensor.
- *inputs*: state, legal moves, action history for episode
- *outputs*: tensor for the encoded form of the adapted state

To be imported into the elsciRL GUI tool, the class name must be *'Adapter'*.

```python
# numeric adapter (numeric.py)
class Adapter(setup_info):
  def __init__():
    # Determine discrete environment size: e.g. "4x4" => 16 positions
    # Initialize a StateEncoder for these positions
    # Optionally define an observation space (e.g., Discrete) needed for Gym agents

  def adapter(state, legal_moves=[], episode_action_history=[], encode=True, indexed=False):
    # If encode=True, convert the numeric state to a tensor (StateEncoder)
    # If indexed=True, map states to integer IDs

	return tensor(state_encoded)
```


#### Language Adapters

```python
# Import language transformer from elsciRL 
from elsciRL.encoders.language_transformers.MiniLM_L6v2 import LanguageEncoder

# numeric adapter (numeric.py)
class Adapter(setup_info):
  def __init__():
	# Initialize the language transformer
    self.encoder = LanguageEncoder()
    # Get variables from encoder
    # - Observation space is used for compatibility with other RL agent libraries
    # - Output dim is required to used for the input of neural agents
    self.observation_space = self.encoder.observation_space
    self.output_dim = self.encoder.output_dim

	# Specify the language adapter, e.g.:
	
	# - directly map state_id or x_y to text
	self.stateID_language = {
		'0':'You are in a hallway, next to you is a door',
		'1':'...',
	}
	self.x_y_language = {
		'0_1':'You are in a hallway, next to you is a door',
		'0_2':'...',
	}
    

  def adapter(state, legal_moves=[], episode_action_history=[], encode=True, indexed=False):
	# 1. Transform observed data to language
	# - Map state
	state = self.obs_mapping[state]
	# - Add legal moves or action history information, e.g. last action taken
	if len(episode_action_history)>0:
		state = state + ' '+ episode_action_history[-1] + '.'
		
	# 2. Encode text using language transformer
	# - If encode=True, convert the numeric state to a tensor (StateEncoder)
	# - else, return raw state text (used by instruction following approaches)
	if encode:
		state_output = self.encoder(state=state)
	else:
		state_output = state
		
	# - likewise indexed state if indexed=True, map states to integer IDs
	if (indexed):
		state_indexed = list()
		for sent in state:
			if (sent not in Adapter._cached_state_idx):
				Adapter._cached_state_idx[sent] = len(Adapter._cached_state_idx)
				state_indexed.append(Adapter._cached_state_idx[sent])
		self.state_indexed = torch.tensor(state_indexed)

	return state_output
```