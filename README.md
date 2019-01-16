# conceptswebengine
An free/libre/opensource software project to provide an Engine for www/html Interactive Presentations of Concepts Database/Knowledgebase for businesses, individuals, groups, etc.

```
branch master_java:

interface LinkedConcepts {…}
interface ConceptInteractivePresentation {…}
interface Concept {…}
interface ConceptPresenter {
  ConceptInteractivePresentation getPresentation(Concept concept, Object context);
}

interface Startable { void start(Object context); }
interface ShuttableDown { void shutdown(Object context); }
interface Testable { void test(Object context); }
interface StressTestable { void stressTest(Object context); }
interface Engine {/* intentionally empty*/}
enum ContinuousIntegrationServerInstanceType { 
  productionServer, testServer, stressTestServer, developmentServer 
}
interface ServerInstance {
  ContinuousIntegrationServerInstanceType getServerInstanceType(Object context);
}
interface ManageableEngine extends Engine, Startable, ShuttableDown, ServerInstance
  /*, … — list of capabilities might be expanded*/ {}
interface TestableManageableEngine extends ManageableEngine, Testable, StressTestable {}
```
