# elsciRL GUI Application Guide

<div align="center">
    <iframe width="700" height="400"  
        src="https://www.youtube.com/embed/JbPtl7Sk49Y">  
    </iframe>
</div>

## Overview

The elsciRL GUI is a web-based application that allows you to run reinforcement learning experiments with various agents and adapters. The interface is organized into five main tabs, each serving a specific purpose in the experiment workflow.

## Workflow Best Practices

### 1. Start with Application Selection
- Choose an application that matches your research goals
- Review preview images to understand the problem structure
- Select appropriate configuration options

### 2. Configure Your Experiment
- Import preset configurations when available
- Set reasonable training/testing parameters
- Select multiple agents for comparison
- Configure agent parameters based on problem characteristics

### 3. Provide Clear Instructions
- Use the LLM Instruction Planner for validation
- Write specific, actionable instructions
- Validate agent understanding before training
- Iterate on instructions if needed

### 4. Monitor Training Progress
- Watch real-time updates during training
- Note any warnings or errors
- Allow sufficient time for completion

### 5. Analyze Results Thoroughly
- Review all generated figures and metrics
- Compare performance across agents
- Consider variance in results
- Save configurations for reproducibility

## Tips for Success

- **Start Simple**: Begin with basic configurations and gradually add complexity
- **Use Presets**: Leverage published configurations as starting points
- **Validate Instructions**: Always confirm agent understanding before training
- **Monitor Resources**: Ensure your system has sufficient computational resources
- **Save Configurations**: Export successful configurations for future use
- **Compare Agents**: Always run multiple agents to understand relative performance
- **Check Logs**: Review training logs for insights into agent behavior

## Troubleshooting

- **Training Fails**: Check agent parameters and ensure sufficient episodes
- **Poor Performance**: Try different agent configurations or instruction sets
- **Slow Training**: Reduce episode count or use simpler agents
- **Memory Issues**: Lower batch sizes or use smaller networks
- **Instruction Problems**: Use the LLM Instruction Planner for validation

This GUI provides a comprehensive interface for running reinforcement learning experiments with language instruction capabilities. Follow the workflow systematically, and you'll be able to conduct sophisticated RL experiments with ease.

## Tab-by-Tab Guide

### 1. Application Tab

The **Application** tab is where you configure your experiment environment:

#### Application Selection
- **Select Application**: Choose from available reinforcement learning environments/problems
- Available applications include various RL environments and problem types

#### Configuration Options (appear after selecting an application)
- **Local Config**: Choose a preset problem configuration for your selected application
- **Observed State Input**: Select pre-rendered observed state data used by instruction-following methods
- **Select Analysis File**: Choose a preset, problem-specific analysis script for results visualization

#### Preview Features
- **Preview Images**: View visual representations of the selected application
- **Image Selection**: Browse through different preview images to understand the environment

**What to do here:**
1. Select your desired application/environment
2. Choose appropriate configuration options based on your experiment needs
3. Review preview images to understand the problem structure
4. Ensure all required fields are populated before proceeding

### 2. Config Tab

The **Config** tab handles experiment configuration and agent setup:

#### Import/Export Configuration
- **Published Configs**: Choose from preset experiment configurations
- **Import Config**: Upload a JSON configuration file from your computer
- **Export Config**: Save your current configuration as a JSON file for future use

#### Training Configuration
- **Training Episodes**: Number of episodes for training (10-10,000, default: 1000)
- **Training Repeats**: Number of times to repeat training with the same starting position (1-100, default: 5)

#### Testing Configuration
- **Test Episodes**: Number of episodes for testing (1-1000, default: 200)
- **Test Repeats**: Number of times to repeat testing (1-100, default: 10)

#### Agent and Adapter Selection
Available agents include:
- **Q-Learning**: Traditional Q-learning algorithm
- **Deep Q-Network (DQN)**: Neural network-based Q-learning
- **LLM Ollama Local**: Language model-based agent using local Ollama

For each selected agent, you can:
- Choose from available adapters
- Configure agent-specific parameters (learning rates, network sizes, etc.)

#### Agent Parameters
Each agent has specific configurable parameters:

**Q-Learning Parameters:**
- Learning Rate (Alpha): 0-1, default: 0.1
- Discount Factor (Gamma): 0-1, default: 0.95
- Exploration Rate (Epsilon): 0-1, default: 0.2
- Epsilon Step: 0-1, default: 0.01

**DQN Parameters:**
- Hidden Layer Size: 32+, default: 128
- Learning Rate: 0-1, default: 0.001
- Discount Factor (Gamma): 0-1, default: 0.99
- Initial Exploration Rate: 0-1, default: 1.0
- Minimum Exploration Rate: 0-1, default: 0
- Epsilon Decay Rate: 0-1, default: 0.995
- Replay Memory Size: 1000+, default: 10000
- Batch Size: 1+, default: 64
- Target Network Update Frequency: 1+, default: 10

**LLM Ollama Parameters:**
- Epsilon: 0-1, default: 0.2
- Model Name: default: "qwen3:0.6b"
- Context Length: default: "1000"
- System Prompt: Custom system prompt for the LLM
- Previous State Action History Length: 1+, default: 10
- Action Language Mapping: Boolean, default: False

**What to do here:**
1. Optionally import a preset configuration or export your current one
2. Set training and testing parameters based on your experiment needs
3. Select the agents you want to compare
4. Choose appropriate adapters for each agent
5. Configure agent-specific parameters for optimal performance

### 3. Instruction Input Tab

The **Instruction Input** tab allows you to provide language instructions to guide your agents:

#### Instruction Management
- **Import Instructions**: Select from available instruction sets for your application
- **Reset All Instructions**: Clear all current instructions and validation states
- **Instruction Preset Status**: Shows when a preset is active and allows clearing it

#### LLM Instruction Planner
- **Enable LLM Instruction Planner**: Toggle to use AI-powered instruction validation
- **LLM Model**: Specify the LLM model to use (default: "llama3.2")
- **Context Length**: Set the context length for the LLM (default: 32000)
- **Number of Instructions**: Specify how many instructions to generate (1-9, default: 1)

#### Input Interface
- **User Input**: Text area for entering your instructions
- **Submit**: Process your instructions and see how the agent interprets them
- **New Instruction**: Start a fresh instruction set

#### Validation Interface
- **Console Output**: Shows how the agent interprets your instructions
- **Confirmation Buttons**: 
  - When LLM Planner is disabled: "Correct" or "Incorrect"
  - When LLM Planner is enabled: "Agree with LLM" or "Disagree with LLM"
- **Instruction Match Plots**: Visual representations of instruction matching

#### Additional Features
- **Additional Preview Images**: More visual context for your instructions
- **Instruction Match Plots**: Visual feedback on instruction effectiveness

**What to do here:**
1. Optionally import existing instruction sets or create your own
2. Enable LLM Instruction Planner for AI-assisted validation
3. Enter clear, specific instructions for your agent
4. Submit and review how the agent interprets your instructions
5. Confirm whether the interpretation is correct
6. Iterate on instructions until satisfied

### 4. Train Model Tab

The **Train Model** tab is where you execute your experiment:

#### Experiment Control
- **Run Experiment**: Start the training process with your current configuration
- **Experiment Instructions**: Guidance on what happens when you run the experiment

#### Real-time Monitoring
- **Training Progress**: Real-time updates on experiment progress
- **Recent Training Log**: Live feed of training messages and status updates
- **Real-time Render Display**: 
  - Phase titles showing current processing stage
  - Live figure updates as results are generated
  - Status indicators for experiment progress

#### Training Log
- **Full Training Log**: Complete log of all training activities
- **Error Handling**: Clear indication of any issues during training

**What to do here:**
1. Review your configuration to ensure everything is set correctly
2. Click "Run Experiment" to start training
3. Monitor the real-time progress indicators
4. Watch for any error messages or warnings
5. Wait for completion before proceeding to Results

### 5. Results Tab

The **Results** tab displays your experiment outcomes:

#### Instructions Summary
- **Validated Instructions**: Shows the instructions that were used in training
- **Instruction Details**: Breakdown of each instruction and its validation status

#### Problem-Specific Results
- **Analysis Figures**: Generated plots and visualizations specific to your problem
- **Performance Metrics**: Results showing agent performance
- **Comparative Analysis**: Side-by-side comparisons of different agents

#### Variance Analysis
- **Full Variance Analysis**: Statistical analysis of performance variance
- **Reliability Metrics**: Measures of result consistency across runs
- **Visual Charts**: Graphical representations of variance data

**What to do here:**
1. Review the instructions that were actually used in training
2. Examine problem-specific results and performance metrics
3. Analyze variance in performance across different runs
4. Compare results between different agents and configurations
5. Export or save results for further analysis



