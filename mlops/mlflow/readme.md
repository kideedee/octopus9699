Getting Started with MLflow
***
# I. What is MLflow?
- Stepping into the world of Machine Learning is an exciting journey, but it often comes with complexities that can hinder innovation and experimentation.
- MLflow is a solution to many of these issues in this dynamic landscape, offering tools and simplifying processes to streamline the ML lifecycle and foster collaboration among ML practitioners.

# II. Core Components of MLflow
MLflow, at its core, provides a suite of tools aimed at simplifying the ML workflow. Its functionalities are rooted in several foundational components:
1. **Tracking** - provides both an API and UI dedicated to the logging of parameters, code versions, metrics, and artifacts during the ML process. Tracking facilitates the logging of results either to local files or a server, making it easier to compare multiple runs across different users.
2. **Model Registry** - A systematic approach to model management. The model Registry assists in handling different versions of models. It provides APIs and UI to collaboratively manage an MLflow Model's full lifecycle, including model lineage, versioning, aliasing, tagging, and annotations.
3. **MLflow Deployments for LLMs** - This server, equipped with a set of standardized APIs, streamlines access to both SaaS and OSS LLM models. It serves as a unified interface, bolstering security through authenticated access, and offers a common set of APIs for prominent LLMs.
4. **Evaluate** - Designed for in-depth model analysis, this set of tools facilities objective model comparison
5. **Prompt Engineering UI** - A dedicated environment for prompt engineering, this UI-centric component provides a space for prompt experimentation, refinement, evaluation, testing, and deployment.
6. **Recipes** - Serving as a guide for structuring ML projects, Recipes, while offering recommendations, are focused on ensuring functional and results optimized for real-world deployment scenarios
7. **Projects** MLflow Projects standardize the packaging of ML code, workflows, and artifacts, akin to an executable. Each project, be it a directory with code or a Git repository, employs a descriptor or convention to define its dependencies and execution method.
