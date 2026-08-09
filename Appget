# calculator_get.py
# A simple calculator with add, subtract, multiply, divide using GET methods
from fastapi import FastAPI, Query
import uvicorn
from pydantic import BaseModel


# Create FastAPI instance with metadata for documentation
app = FastAPI(
    title="Calculator API (GET)",
    description="A simple calculator API with add, subtract, multiply and divide operations using GET requests",
    version="0.2.0"
)

class CalculationResult(BaseModel):
    operation: str
    a: float
    b: float
    result: float


@app.get("/add", response_model=CalculationResult)
def add(a: float = Query(..., description="First number"), b: float = Query(..., description="Second number")):
    """Add two numbers and return the result."""
    result = a + b
    return CalculationResult(operation="add", a=a, b=b, result=result)


@app.get("/subtract", response_model=CalculationResult)
def subtract(a: float = Query(..., description="First number"), b: float = Query(..., description="Second number")):
    """Subtract b from a and return the result."""
    result = a - b
    return CalculationResult(operation="subtract", a=a, b=b, result=result)


@app.get("/multiply", response_model=CalculationResult)
def multiply(a: float = Query(..., description="First number"), b: float = Query(..., description="Second number")):
    """Multiply two numbers and return the result."""
    result = a * b
    return CalculationResult(operation="multiply", a=a, b=b, result=result)


@app.get("/divide", response_model=CalculationResult)
def divide(a: float = Query(..., description="First number"), b: float = Query(..., description="Second number")):
    """Divide a by b and return the result."""
    result = a / b
    return CalculationResult(operation="divide", a=a, b=b, result=result)


@app.get("/")
def read_root():
    """Root endpoint that returns a welcome message."""
    return {"message": "Calculator API is running. Use /add, /subtract, /multiply or /divide endpoints with query params a and b."}


# Main program
if __name__ == "__main__":
    uvicorn.run(app, host="localhost", port=9321)
