## Contributing to FloydHub Documentation

### Topics
- Tutorials

    Tutorials that get the user started with FloydHub. The tutorials should be complete (user should have something to see or show at the end), while introducing new concepts progressively. 
    
    They should focus on a high level task, like training a CNN for Neural Style Transfer on FloydHub, while deferring concept deep dives to the Guides (below).

    - [ ] **Quick Start**: A very quick intro (2 minute read) to give the users their first success ASAP. Introduce the 5 basic commands to train a simple neural network model (say MNIST) using FloydHub.
    - [X] **First Project**: A more detailed guide to training your first CNN using Tensorflow. Introduces some fundamental concepts:
        - [ ]: `floyd-cli` vs. Web dashboard
        - [ ]: Initializing an existing project (`quick-start`) on your computer
        - [ ]: Using the `floyd run` command to train a deep learning model on FloydHub's GPU servers
        - [ ]: Viewing the job status, the output logs and results, using the CLI and dashboard
    - [ ] **Detailed Guide**: 
        - [ ]: Create a new dataset
        - [ ]: Upload new dataset from CLI
        - [ ]: Mount multiple datasets
        - [ ]: Reuse output from previous job
        - [ ]: Executign multiple commands using a bash script
        - [ ]: Deleting job, data, project
        - [ ]: `floyd_requirements.txt`
        - [ ]: `.floydignore`
        - [ ]: Downloading output of a job
        - [ ]: Serving

- Guides 

    Guides are focused articles that guide the user to perform common tasks. Some examples of good guides are Github's [Forking Projects](https://guides.github.com/activities/forking/) and Heroku's [Deploying with Git](https://devcenter.heroku.com/articles/git).

    - Basics
        - [ ]: Core concepts
            - [ ]: Introduce project, job, dataset, data
            - [ ]: Lifecycle of a job (queued, running, timeout, shutdown) and data (pending, valid, corrupt)
        - [X]: Install Floyd CLI
        - [X]: Login using Floyd CLI
        - [ ]: Create and Delete:
            - [ ]: Create new project, delete project
            - [ ]: Create new dataset, delete dataset
        - [ ]: Running a job using `floyd run`
            - Examples of common scenarios
            - Stopping a job
            - Using the `--message` (or `-m`) flag with each `floyd run` command to attach a "job message" (similar to *commit message*) to each job. This will show up in the job dashboard
        - [ ]: Viewing output logs using CLI and dashboard
        - [ ]: Mounting data
            - Note that data mount paths are absolute, not relative
            - Using symbolic links (`cp --symbolic-link ../foo/* .`) to copy mounted data to the location expected by the code
        - [ ]: Saving data
        - [ ]: Separation of code and data

    - Intermediate
        - [ ]: Installing dependencies
            - [ ]: `floyd_requirements.txt`
        - [ ]: Tensorboard
            - [ ]: Using Tensorboard offline with output checkpoints
        - [ ]: `.floydignore`

    - Advanced
        - [ ]: Executing multiple commands using a bash script
        - [ ]: Check GPU status using `nvidia-smi` command
        - [ ]: Saving and using Tensorflow checkpoints
        - [ ]: Best practices:
            - [ ]: Load dataset into memory before processing using GPU
        - [ ]: Benchmarks:
            - [ ]: Benchmark CPU vs. GPU on FloydHub
            - [ ]: Benchmark I/O intensive vs. memory intensive
        - [ ]: Example documentation for algorithm development (vs. running an existing project): Debugging, logging internals, etc.
        - [ ]: Using Tensorboard from Keras and PyTorch

- Commands
- Environments
- FAQs
- Short Videos

    Introductory videos (screen recordings with audio commentary) that teach users some common workflows. These could be walkthroughs that cover a complete topic. Or they could cover complex or abstract concepts, like debugging, that are difficult to write about without being verbose.

    They should be 1-2 mins for shorter topics, and under 10 mins in all cases. Examples: [Domino Data Lab](https://support.dominodatalab.com/hc/en-us)

- Contributing Guide

    Write a short guide on how to make pull requests to improve docs

    

- Sample Projects

### Sites with great documentation

- SendGrid: [https://sendgrid.com/docs](https://sendgrid.com/docs)
- TensorPort: [https://tensorport.com/documentation/](https://tensorport.com/documentation/)


## Notes

- When restructuring pages, make sure to add redirects from the old page. Old fashioned redirects, like "This page has now been moved to {{new_location}}" should work. Also ensure that the redirect page is not listed in the table of contents