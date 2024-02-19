# Architecture Principles

The following are high-level architecture principles that we shall apply to the architecture of MonitorMe

| Principle     |Rationale         | Impact    |
| ------------ | ----------------- |  -------------- |
| Наш архитектурный стиль| ссылка на ADR |
| Data is important| Our system data oriented and this data is important for Patient Health | Soltions must consider realibility and consistency as main priorites.
| Security in | Our system operate sensitive and personal data | Any requiremetns to systems should be started from security analyes in order to identify which data and whom will be available
| Compliant with law and regulation | System will be used in Hospitals | Related Regualtions should be taken as must have requirements even in very first release.
| System should be extendable | Solution developed of Medical domain, it very fast developing area and we start this application form scratch and expect a lot of feedbacks from market | Modules of system should use plug-in or adapter patterns for allow replace part of solution and extend with new functinality.
|System should be Maintainable| Part of system deployed on-premises | System should be ready that not techincal export will  administrate it.



