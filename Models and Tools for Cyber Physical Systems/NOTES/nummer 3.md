![[Pasted image 20240221081759.png]]
# Safety
- Nothing bad ever happens
# Liveness
- something good will eventually happen.
- analysens liveness is often harder.

![[Pasted image 20240221081738.png]]
![[Pasted image 20240221083950.png]]
# Dynamic vs. Static Analysis 
-  Dynamic analysis (runtime) 
	- Execute the system multiple times with different inputs 
	- Check if every execution meets the desired requirement 
- Static analysis (design time) 
	-  Analyze the source code or the model for possible bugs 
- Trade-offs 
	- Dynamic analysis is incomplete, but accurate (checks real system, bugs discovered are real bugs) 
	- Static analysis can catch design bugs early 
	- Static analysis is not always scalable (solution: analyze approximate versions, which can lead to false warnings)
