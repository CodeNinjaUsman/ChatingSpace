# Using the State Hook

The [introduction page](https://reactjs.org/docs/hooks-intro.html) used this example to get familiar with Hooks:

<Code language="python">
#!/usr/bin/env python
"""Django's command-line utility for administrative tasks."""
import os
import sys


def main():
    """Run administrative tasks."""
    os.environ.setdefault('DJANGO_SETTINGS_MODULE', 'Blog.settings')
    try:
        from django.core.management import execute_from_command_line
    except ImportError as exc:
        raise ImportError(
            "Couldn't import Django. Are you sure it's installed and "
            "available on your PYTHONPATH environment variable? Did you "
            "forget to activate a virtual environment?"
        ) from exc
    execute_from_command_line(sys.argv)


if __name__ == '__main__':
    main()

</Code>

We’ll start learning about Hooks by comparing this code to an equivalent class example.

# Equivalent Class Example

If you used classes in React before, this code should look familiar:

<Code language="javascript">
class Example extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0
    };
  }

  render() {
    return (
      &lt;div>
        &lt;p>You clicked {this.state.count} times</p>
        &lt;button 
          onClick={() => this.setState({ count: this.state.count + 1 })}>
          Click me
        </button>
      </div>
    );
  }
}
</Code>

The state starts as `{ count: 0 }`, and we increment state.count when the user clicks a button by calling `this.setState()`. We’ll use snippets from this class throughout the page.

> ***Note***
>
> You might be wondering why we’re using a counter here instead of a more realistic example. This is to help us focus on the API while we’re still making our first steps with Hooks.
