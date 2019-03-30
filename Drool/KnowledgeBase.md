## Knowledge Base ##

Knowledge base is a collection of compiled predefined rules. Use KnowledgeBuilder to compile rules.  
```
KnowledgeBuilder kbuilder = KnowledgeBuilderFactory.newKnowledgeBuilder();

kbuilder.add( ResourceFactory.newClassPathResource( "licenseApplication.drl", getClass() ),

              ResourceType.DRL );

if ( kbuilder.hasErrors() ) {

    System.err.println( kbuilder.getErrors().toString() );

}

KnowledgeBase kbase = KnowledgeBaseFactory.newKnowledgeBase();

kbase.addKnowledgePackages( kbuilder.getKnowledgePackages() );
```
