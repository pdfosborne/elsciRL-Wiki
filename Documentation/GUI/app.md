<!-- filepath: /home/philip/Documents/elsciRL-Wiki/Documentation/GUI/app.md -->

# elsciRL GUI Web Application

This module provides a Flask-based web interface for the elsciRL framework, allowing users to interactively configure, run, and analyze RL experiments through a browser.

## Main Class: `WebApp`

### Features
- Application and agent selection via a web interface
- Dynamic configuration of experiments and agent parameters
- Integration with LLM-based instruction following and validation
- Visualization of results and download of experiment outputs
- File upload and management for custom configurations
- Asynchronous job management for long-running tasks

### Key Endpoints
- `/` : Home page (experiment setup and dashboard)
- `/process_input` : Process user input and run experiments
- `/train_model` : Start model training
- `/results` : Search and display results
- `/upload` : Upload configuration or data files
- `/get_applications`, `/get_adapters`, `/get_local_configs`, etc.: API endpoints for dynamic UI population

### Usage Example

To run the GUI app:

```python
from elsciRL import App
App.run()
```

Then open your browser and navigate to `http://127.0.0.1:5000/` to access the interface.

### Example Workflow
1. Select an application and agent type from the dropdown menus.
2. Configure agent parameters and experiment settings.
3. Upload any custom configuration files if needed.
4. Start training or evaluation jobs and monitor progress.
5. View and download results, plots, and reports from the web interface.

---