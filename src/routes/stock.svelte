<script>
    import {
        Accordion,
        AccordionItem,
        Content,
        Grid,
        Row,
        Column,
        Link,
    } from "carbon-components-svelte";
    import "carbon-components-svelte/css/white.css";
</script>

<Content>
    <Grid style="margin-bottom: 5%">
        <Row>
            <Column style="margin-bottom: 2%">
                <h1>TSLA</h1>
            </Column>
        </Row>
        <Row>
            <Column style="margin-bottom: 5%">
                <Accordion size="xl">
                    <AccordionItem title="Search">
                        <p>
                            Natural Language Classifier uses advanced natural
                            language processing and machine learning techniques
                            to create custom classification models. Users train
                            their data and the service predicts the appropriate
                            category for the inputted text.
                        </p>
                    </AccordionItem>
                    <AccordionItem title="Summary">
                        <p>
                            Analyze text to extract meta-data from content such
                            as concepts, entities, emotion, relations, sentiment
                            and more.
                        </p>
                    </AccordionItem>
                    <AccordionItem title="Sentiment">
                        <p>
                            Translate text, documents, and websites from one
                            language to another. Create industry or
                            region-specific translations via the service's
                            customization capability.
                        </p>
                    </AccordionItem>
                    <AccordionItem title="Highlights">
                        <p>
                            Translate text, documents, and websites from one
                            language to another. Create industry or
                            region-specific translations via the service's
                            customization capability.
                        </p>
                    </AccordionItem>
                    <AccordionItem title="Connections">
                        <p>
                            Translate text, documents, and websites from one
                            language to another. Create industry or
                            region-specific translations via the service's
                            customization capability.
                        </p>
                    </AccordionItem>
                    <AccordionItem title="Distil">
                        <p>
                            Translate text, documents, and websites from one
                            language to another. Create industry or
                            region-specific translations via the service's
                            customization capability.
                        </p>
                    </AccordionItem>
                </Accordion>
            </Column>
        </Row>
        <Row style="margin-bottom: var(--cds-layout-02)">
            <Column>
                <h3>Installation</h3>
            </Column>
        </Row>
    </Grid>
</Content>
