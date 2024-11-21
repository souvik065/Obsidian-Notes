

To calculate β0\beta_0β0​ (intercept) and β1\beta_1β1​ (slope) for a simple linear regression, follow these steps:

---

### **1. Regression Equation**

The regression line is:

$y=β0+β1x+εy = \beta_0 + \beta_1 x + \varepsilony=β0​+β1​x+ε$

Where:

- yyy: Dependent variable (e.g., consumption).
- xxx: Independent variable (e.g., income).
- β1\beta_1β1​: Slope of the line.
- β0\beta_0β0​: Intercept of the line.

---

### **2. Formulas**

- **Slope (β1\beta_1β1​):**

$β1=∑(xi−xˉ)(yi−yˉ)∑(xi−xˉ)2\beta_1 = \frac{\sum (x_i - \bar{x})(y_i - \bar{y})}{\sum (x_i - \bar{x})^2}β1​=∑(xi​−xˉ)2∑(xi​−xˉ)(yi​−yˉ​)​$

Where:

- $xi,yix_i, y_ixi​,yi$​: Individual data points.
    
- xˉ,yˉ\bar{x}, \bar{y}xˉ,yˉ​: Mean of xxx and yyy.
    
- **Intercept (β0\beta_0β0​):**
    

β0=yˉ−β1xˉ\beta_0 = \bar{y} - \beta_1 \bar{x}β0​=yˉ​−β1​xˉ

---

### **3. Steps to Calculate Manually**

1. **Compute means (xˉ\bar{x}xˉ and yˉ\bar{y}yˉ​):**
    
    xˉ=∑xin,yˉ=∑yin\bar{x} = \frac{\sum x_i}{n}, \quad \bar{y} = \frac{\sum y_i}{n}xˉ=n∑xi​​,yˉ​=n∑yi​​
2. **Calculate the numerator and denominator for β1\beta_1β1​:**
    
    Numerator: ∑(xi−xˉ)(yi−yˉ)\text{Numerator: } \sum (x_i - \bar{x})(y_i - \bar{y})Numerator: ∑(xi​−xˉ)(yi​−yˉ​) Denominator: ∑(xi−xˉ)2\text{Denominator: } \sum (x_i - \bar{x})^2Denominator: ∑(xi​−xˉ)2
3. **Find β1\beta_1β1​:**
    
    β1=NumeratorDenominator\beta_1 = \frac{\text{Numerator}}{\text{Denominator}}β1​=DenominatorNumerator​
4. **Calculate β0\beta_0β0​:**
    
    β0=yˉ−β1xˉ\beta_0 = \bar{y} - \beta_1 \bar{x}β0​=yˉ​−β1​xˉ

---

### **4. Example Calculation**

Suppose we have the following data:

|Income (xxx)|Consumption (yyy)|
|---|---|
|50|30|
|60|35|
|70|40|
|80|45|
|90|50|

1. **Compute Means:**
$xˉ=50+60+70+80+905=70\bar{x} = \frac{50 + 60 + 70 + 80 + 90}{5} = 70xˉ=550+60+70+80+90​=70 yˉ=30+35+40+45+505=40\bar{y} = \frac{30 + 35 + 40 + 45 + 50}{5} = 40yˉ​=530+35+40+45+50​=40$
2. **Calculate β1\beta_1β1​:**

Numerator $∑(xi−xˉ)(yi−yˉ)=(50−70)(30−40)+(60−70)(35−40)+⋯=500\text{Numerator: } \sum (x_i - \bar{x})(y_i - \bar{y}) = (50-70)(30-40) + (60-70)(35-40) + \dots = 500Numerator: ∑(xi​−xˉ)(yi​−yˉ​)=(50−70)(30−40)+(60−70)(35−40)+⋯=500 Denominator: ∑(xi−xˉ)2=(50−70)2+(60−70)2+⋯=1000$\text{Denominator: } \sum (x_i - \bar{x})^2 = (50-70)^2 + (60-70)^2 + \dots = 1000Denominator: ∑(xi​−xˉ)2=(50−70)2+(60−70)2+⋯=1000 β1=5001000=0.5\beta_1 = \frac{500}{1000} = 0.5β1​=1000500​=0.5:$$ 
3. **Calculate β0\beta_0β0​:**
    
    β0=yˉ−β1xˉ=40−(0.5)(70)=5\beta_0 = \bar{y} - \beta_1 \bar{x} = 40 - (0.5)(70) = 5β0​=yˉ​−β1​xˉ=40−(0.5)(70)=5$$



### **5. Final Equation**

y=5+0.5xy = 5 + 0.5xy=5+0.5x

This means for every unit increase in income, consumption increases by 0.5 units, starting from a base consumption of 5 when income is zero.


Reference :
[ChatGpt](https://chatgpt.com/share/673ccc78-9160-8012-925b-2ab4e7ff99cb)