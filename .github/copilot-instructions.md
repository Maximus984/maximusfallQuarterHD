# AI Agent Instructions for Maxfallquater Project

This project is a Flask-based web application that serves as an educational platform for business planning and entrepreneurship resources.

## Project Structure

```
.
├── app.py              # Flask application entry point
├── requirements.txt    # Python dependencies
├── Rse/               # Business education content
│   └── week{5,6,7}/   # Weekly lesson content
├── static/            # Static assets
│   ├── css/          # Stylesheets
│   ├── images/       # Image assets
│   └── js/           # JavaScript files
└── templates/         # Jinja2 templates
```

## Key Technologies

- **Flask 3.0.0**: Web framework
- **Jinja2 3.1.2**: Template engine
- **Werkzeug 3.0.1**: WSGI utilities

## Architecture Patterns

1. **Template Inheritance**
   - Base template: `templates/base.html`
   - All pages should extend the base template using `{% extends 'base.html' %}`
   - Content goes in the `{% block content %}` section

2. **Static Asset Organization**
   - CSS: Use `style.css` for custom styles
   - JS: Add custom JavaScript to `main.js`
   - Reference static files using `url_for('static', filename='path/to/file')`

## Development Workflow

1. **Local Development**
   ```bash
   # Install dependencies
   pip install -r requirements.txt
   
   # Run development server
   python app.py  # Runs on http://localhost:5000 with debug mode
   ```

2. **Adding New Routes**
   - Add route decorators in `app.py`
   - Create corresponding templates in `templates/`
   - Example:
   ```python
   @app.route('/new-path')
   def new_path():
       return render_template('template.html', title='Page Title')
   ```

## Content Organization

- Business education content lives in the `Rse/` directory
- Weekly lessons are organized in numbered subdirectories
- Markdown files follow naming pattern: `L{number}_{topic}.md`

## Best Practices

1. **Template Variables**
   - Always provide a `title` parameter when rendering templates
   - Example: `render_template('base.html', title='Home')`

2. **Static Assets**
   - Keep styles organized in `style.css`
   - Add new JavaScript modules in `static/js/`
   - Use semantic class names for styling

## Important Notes

- The application uses Flask's debug mode in development
- Business content is structured as weekly lessons with specific focus areas
- Static files are served automatically from the `static/` directory