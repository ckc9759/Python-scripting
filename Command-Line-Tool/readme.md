### N o T e S

---

- Typer --> helps build CLIs. 

```py
import typer

app=typer.Typer()

@app.command()
def h(name : str, iq : int, display_iq : bool = True):
    print(f"Hello {name}")
    if display_iq :
    print(f"Your iq is {iq}")
    
@app.command()
def g():
    print("Goodbye")

if __name__ == "__main__":
    app()
```

