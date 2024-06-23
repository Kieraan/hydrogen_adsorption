# hydrogen_adsorption

## Spherical Adsorption Lumped Parameter Model
Notebook that solves a hydrogen adsorption system in spherical coordinates. This is a quick implementation that tests the capabilities of Julia to solve differential system of equations that includes algebraic equations. 

### Equations
Algebraic equations: 

$$ n_A = n_0 \exp \left[ {\left(-\frac{RT}{{\alpha + \beta T}}\right)^m \ln^m\left(\frac{p_0}{p}\right)} \right]$$

$$ f(n_A) =  n_A - n_0 \exp {\left(-\frac{RT}{{\alpha + \beta T}}\right)^m \ln^m\left(\frac{p_0}{p}\right)}  $$

$$ p = \frac{\rho R T}{M_{H_2}}$$

Mass differential equations 

$$ \frac{d \rho_{H_2}}{d t} = \frac{\dot{m}_s}{V \varepsilon} - \frac{(1 - \varepsilon) \rho M_{H_2}}{\varepsilon}$$

Lumped parameter temprature differential equation (Xiao, 2013):

$$ 
(c_{ps} \rho_{s} \varepsilon + \rho_b c_{pp}(1-\varepsilon)) \frac{dT}{dt} = \dot{m_s}h_s + \frac{dm_a}{dt} \frac{\Delta{H}}{M_{H_2}} + h_f A_e (T-T_f)
$$

This equations is a modification of the temperature ODE found in [Lumped parameter model for charge–discharge cycle of adsorptive
hydrogen storage system](https://doi.org/10.1016/j.ijheatmasstransfer.2013.04.029). It follows the same equation but ignores the tank capacity to transfer heat and assumes constant isosteric heat of adsorption.  
