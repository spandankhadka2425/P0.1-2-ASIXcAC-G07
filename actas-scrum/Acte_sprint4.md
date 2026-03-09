## Sprint 4 - Acta Sprint Planning

**Fecha:** 17/02/2026 - 24/02/2026

El día **17/02/2026** hemos realizado el **Sprint Planning para Sprint 4**. En esta reunión participaron:

**Participantes:**
- Scrum Master: Jan
- Product Owner: Spandan  
- Miembro: Anmol  

**Propósitos del Sprint 4:**  
Implementar **securització completa** de la infraestructura Extagram:  
- Firewall delante S1 (UFW/iptables)  
- Hardening web (WAF nginx)  
- Hardening sistema operativo contenedores  
- Hardening MySQL (privilegios mínimos)  

- [index.md](../index.md)

# Revisión de Tareas

### **5 tareas**

1. **Analizar riesgos de seguridad Extagram**  
   - **Responsable:** Jan  
   - **Fecha de finalización:** 24/02/2026  
   - **Estado:** COMPLETADO 

2. **Probar la web tras el hardening**  
   - **Responsable:** Jan  
   - **Fecha de finalización:** 24/02/2026  
   - **Estado:** COMPLETADO 

3. **Implementar firewall en host Extagram**  
   - **Responsable:** jan  
   - **Fecha de finalización:** 24/02/2026  
   - **Estado:** COMPLETADO 

4. **Diseñar arquitectura de firewall delante de S1**  
   - **Responsable:** Anmol  
   - **Fecha de finalización:** 27/01/2026  
   - **Estado:** COMPLETADO 

5. **Configurar WAF para S1 (hardening web)**  
   - **Responsable:** Spandan, Jan 
   - **Fecha de finalización:** 27/01/2026  
   - **Estado:** PENDIENTE 

4. **Hardening Nginx y PHP en S1/S2/S3/S4**  
   - **Responsable:** Jan  
   - **Fecha de finalización:** 27/01/2026  
   - **Estado:** PENDIENTE 

### **Pendientes de Revisión (Review) – 3 tareas**
tenemos 2 tareas que hemos de acabar en sprint 5

---

## Conclusión del Sprint 4
Hemos tenido bastantes dificultades con la implantación del WAF, ya que inicialmente intentamos montarlo con ModSecurity y esto nos hizo perder mucho tiempo en pruebas y configuraciones que no acababan de funcionar. Finalmente hemos optado por implementar un WAF basado en reglas nativas de nginx.

Este retraso con el WAF ha impactado en el tiempo disponible para la documentación. Como punto de mejora para los próximos sprints, el grupo debe organizar mejor la distribución de tareas y ajustar los plazos de entrega para evitar concentrar demasiado trabajo al final.