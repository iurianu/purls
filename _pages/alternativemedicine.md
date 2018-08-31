---
ID: 176
post_title: Alternative Medicine Ontology
author: iurianu
post_excerpt: ""
layout: page
permalink: https://purls.site/alternativemedicine/
published: true
post_date: 2017-05-16 11:45:15
---
<section class="ontology"
  xmlns:amd="http://purls.site/alternativemedicine/" 
  xmlns:xml="http://www.w3.org/XML/1998/namespace" 
  xmlns:xsd="http://www.w3.org/2001/XMLSchema#"
  xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
  xmlns:rdfs="http://www.w3.org/2000/01/rdf-schema#"
  xmlns:owl="http://www.w3.org/2002/07/owl#"
  xmlns:foaf="http://xmlns.com/foaf/0.1/"
  xmlns:gr="http://purl.org/goodrelations/v1#"
  xmlns:pto="http://www.productontology.org/id/"
  xmlns:dc="http://purl.org/dc/elements/1.1/"
  xmlns:dcterms="http://purl.org/dc/terms/"
  xmlns:schema="http://schema.org/"
  xmlns:geo="http://www.w3.org/2003/01/geo/wgs84_pos#"     
  xmlns:vcard="http://www.w3.org/2006/vcard/ns#"
  xml:base="http://purls.site/alternativemedicine/">
<blockquote id="Ontology" vocab="http://purls.site/alternativemedicine/" typeof="owl:Ontology" resource="amd:Ontology">
<p class="note">You can find a more complete version of this ontology in OWL format <a href="http://purls.site/vocab/Alternative_Medicine.owl" target="_blank">HERE</a>!</p>
<dl>
  <dt>Description: </dt><dd property="owl:description">Ontology created for Spiritual Healing Practice and Practitioners.<br>Encloses: alternative medicine: Energy Healing / Spiritual Healing / Ancient Healing Techniques</dd>
  <dt>Label</dt><dd property="rdfs:label">Alternative Medicine Ontology</dt>
  <dt>Status</dt><dd>Still in development</dt>
  <dt>Language </dt><dd property="xsd:language">English</dd>
  <dt>Author info </dt><dd property="dcterms:creator">Created by kazenokodomo (http://purls.site)</dd>
  <dt>Version Info </dt><dd property="owl:versionInfo">v1.0</dd>
  <dt>Date Issued </dt><dd><time property="dcterms:issued" datetime="2016-05-12">May 12, 2016</time></dd>
  <dt>License Info </dt><dd><a property="dc:license" href="http://creativecommons.org/licenses/by-sa/3.0/" rel="nofollow" title="Creative Commons License">Creative Commons 3.0</a></dd>
  <dt>URI </dt><dd property="rdfs:isDefinedBy">http://purls.site/alternativemedicine/#Ontology</dd>
  <dt>Prefix </dt><dd>amd</dd>
  <dt>xmlns </dt><dd>http://purls.site/alternativemedicine/#</dd>
  <dt>Primary Topic</dt><dd typeof="http://purls.site/alternativemedicine/" resource="amd:Healing">Healing<br></dd>

  <dt>Categories</dt>
  <dd> <a href="#Healing">Healing</a> <a href="#EnergyHealing">EnergyHealing</a> <a href="#SpiritualHealing">SpiritualHealing</a> <a href="#Herbalism">Herbalism</a> <a href="#MindBodyIntervention">MindBodyIntervention</a> <a href="#TraditionalChineseMedicine">TraditionalChineseMedicine</a> <a href="#WesternEuropeMedicine">WesternEuropeMedicine</a> <a href="#Yoga">Yoga</a></dd>
  <dt>Classes</dt>
  <dd><a href="#Acupressure">Acupressure</a> <a href="#Acupuncture">Acupuncture</a> <a href="#AffirmativePrayer">AffirmativePrayer</a> <a href="#AlexanderTechnique">AlexanderTechnique</a> <a href="#AnthroposophicMedicine">AnthroposophicMedicine</a> <a href="#Apitherapy">Apitherapy</a> <a href="#AppliedKinesiology">AppliedKinesiology</a> <a href="#Reiki">Reiki</a>
  </dd>
</dl>
</blockquote>
<hr />

<h3>Category Classes: </h3>
<blockquote typeof="owl:Class" vocab="http://purls.site/alternativemedicine/" id="Healing">
  <h4 property="rdfs:label">Healing</h4>
  <dl>
    <dt>RDF ID </dt><dd property="rdf:ID">Healing</dd>
    <dt>Sub-Class of </dt><dd property="owl:subClassOf" typeof="ProductOrService" vocab="http://purl.org/goodrelations/v1#" resource="http://purl.org/goodrelations/v1#ProductOrService"><a href="http://purl.org/goodrelations/v1#ProductOrService" resource="http://purl.org/goodrelations/v1#ProductOrService">http://purl.org/goodrelations/v1#ProductOrService</a></dd>
    <dt>Sub-Class of </dt><dd property="owl:subClassOf" typeof="MedicalEnumeration" vocab="https://health-lifesci.schema.org/" ><a property="url" href="https://health-lifesci.schema.org/MedicalEnumeration">https://health-lifesci.schema.org/MedicalEnumeration</a></dd>
    <dt>Description </dt><dd property="owl:description">Healing as a complex of activities leading to the improvement of one's health.</dd>
    <dt>Wiki</dt><dd property="foaf:page">https://en.wikipedia.org/wiki/Healing"</dd>
    <dt>URI </dt><dd property="rdfs:isDefinedBy">http://purls.site/alternativemedicine/#Healing</dd>
    <dt>Sub-Classes </dt>
    <dd>
      <a property="dcterms:hasPart" typeof="owl:Class" resource="amd:EnergyHealing" href="#EnergyHealing">EnergyHealing</a> 
      <a property="dcterms:hasPart" typeof="owl:Class" resource="amd:SpiritualHealing" href="#SpiritualHealing">SpiritualHealing</a> 
      <a property="dcterms:hasPart" typeof="owl:Class" resource="amd:Herbalism" href="#Herbalism">Herbalism</a> 
      <a property="dcterms:hasPart" typeof="owl:Class" resource="amd:MindBodyIntervention" href="#MindBodyIntervention">MindBodyIntervention</a> 
      <a property="dcterms:hasPart" typeof="owl:Class" resource="amd:TraditionalChineseMedicine" href="#TraditionalChineseMedicine">TraditionalChineseMedicine</a> 
      <a property="dcterms:hasPart" typeof="owl:Class" resource="amd:WesternEuropeMedicine" href="#WesternEuropeMedicine">WesternEuropeMedicine</a> 
      <a property="dcterms:hasPart" typeof="owl:Class" resource="amd:Yoga" href="#Yoga">Yoga</a> 
    </dd>
  </dl>
</blockquote>
<blockquote typeof="owl:Class" vocab="http://purls.site/alternativemedicine/" id="EnergyHealing">
  <h4 property="rdfs:label">Energy Healing</h4>
  <dl>
    <dt>RDF ID </dt><dd property="rdf:ID">EnergyHealing</dd>
    <dt>Sub-Class of </dt><dd property="owl:subClassOf" typeof="Healing"><a property="rdf:resource" href="#Healing">Healing</a></dd>
    <dt>Description </dt><dd property="owl:description">Energy medicine, energy therapy, energy healing, or spiritual healing are branches of alternative medicine.</dd>
    <dt>URI </dt><dd property="rdfs:isDefinedBy">http://purls.site/alternativemedicine/#EnergyHealing</dd>
  </dl>
</blockquote>
<blockquote typeof="owl:Class" vocab="http://purls.site/alternativemedicine/" id="SpiritualHealing">
  <h4 property="rdfs:label">Spiritual Healing</h4>
  <dl>
    <dt>RDF ID </dt><dd property="rdf:ID">SpiritualHealing</dd>
    <dt>Sub-Class of </dt><dd property="owl:subClassOf" typeof="Healing"><a property="rdf:resource" href="#Healing">Healing</a></dd>
    <dt>Description </dt><dd property="owl:description">The use of spiritual practices for the purpose of effecting a cure of or an improvement in an illness.</dd>
    <dt>URI </dt><dd property="rdfs:isDefinedBy">http://purls.site/alternativemedicine/#SpiritualHealing</dd>
    <dt>Sub-Classes </dt>    
    <dd>
      <a property="dcterms:hasPart" typeof="owl:Class" resource="amd:AffirmativePrayer" href="#AffirmativePrayer">AffirmativePrayer</a> 
    </dd> 
  </dl>
</blockquote>
<blockquote typeof="owl:Class" vocab="http://purls.site/alternativemedicine/" id="Herbalism">
  <h4 property="rdfs:label">Herbalism</h4>
  <dl>
    <dt>RDF ID </dt><dd property="rdf:ID">Herbalism</dd>
    <dt>Sub-Class of </dt><dd property="owl:subClassOf" typeof="Healing"><a property="rdf:resource" href="#Healing">Healing</a></dd>
    <dt>Description </dt><dd property="owl:description">Herbalism is use of plants for medicinal purposes, and the study of such use.</dd>
    <dt>URI </dt><dd property="rdfs:isDefinedBy">http://purls.site/alternativemedicine/#Herbalism</dd>
  </dl>
</blockquote>
<blockquote typeof="owl:Class" vocab="http://purls.site/alternativemedicine/" id="MindBodyIntervention">
  <h4 property="rdfs:label">Mind-Body Intervention</h4>
  <dl>
    <dt>RDF ID </dt><dd property="rdf:ID">MindBodyIntervention</dd>
    <dt>Sub-Class of </dt><dd property="owl:subClassOf" typeof="Healing"><a property="rdf:resource" href="#Healing">Healing</a></dd>
    <dt>Description </dt><dd property="owl:description">Medical and health care systems, practices, and products that are not presently considered part of conventional medicine.</dd>
    <dt>URI </dt><dd property="rdfs:isDefinedBy">http://purls.site/alternativemedicine/#MindBodyIntervention</dd>
    <dt>Sub-Classes </dt>    
    <dd>
      <a property="dcterms:hasPart" typeof="owl:Class" resource="amd:AlexanderTechnique" href="#AlexanderTechnique">AlexanderTechnique</a> 
    </dd>     
  </dl>
</blockquote>
<blockquote typeof="owl:Class" vocab="http://purls.site/alternativemedicine/" id="TraditionalChineseMedicine">
  <h4 property="rdfs:label">Traditional Chinese Medicine</h4>
  <dl>
    <dt>RDF ID </dt><dd property="rdf:ID">TraditionalChineseMedicine</dd>
    <dt>Sub-Class of </dt><dd property="owl:subClassOf" typeof="Healing"><a property="rdf:resource" href="#Healing">Healing</a></dd>
    <dt>Description </dt><dd property="owl:description">Various forms of herbal medicine, acupuncture, massage, exercise, and dietary therapy.</dd>
    <dt>URI </dt><dd property="rdfs:isDefinedBy">http://purls.site/alternativemedicine/#TraditionalChineseMedicine</dd>
    <dt>Sub-Classes </dt>
    <dd>
      <a property="dcterms:hasPart" typeof="owl:Class" resource="amd:Acupressure" href="#Acupressure">Acupressure</a> 
      <a property="dcterms:hasPart" typeof="owl:Class" resource="amd:Acupuncture" href="#Acupuncture">Acupuncture</a> 
    </dd>    
  </dl>
</blockquote>
<blockquote typeof="owl:Class" vocab="http://purls.site/alternativemedicine/" id="WesternEuropeMedicine">
  <h4 property="rdfs:label">Western Europe Medicine</h4>
  <dl>
    <dt>RDF ID </dt><dd property="rdf:ID">WesternEuropeMedicine</dd>
    <dt>Sub-Class of </dt><dd property="owl:subClassOf" typeof="Healing"><a property="rdf:resource" href="#Healing">Healing</a></dd>
    <dt>Description </dt><dd property="owl:description">A mixture of existing ideas from antiquity, identified as spiritual influences, shamanistic complexes, and social consensus.</dd>
    <dt>URI </dt><dd property="rdfs:isDefinedBy">http://purls.site/alternativemedicine/#WesternEuropeMedicine</dd>
    <dt>Sub-Classes </dt>
    <dd>
      <a property="dcterms:hasPart" typeof="owl:Class" resource="amd:Apitherapy" href="#Apitherapy">Apitherapy</a> 
      <a property="dcterms:hasPart" typeof="owl:Class" resource="amd:AppliedKinesiology" href="#AppliedKinesiology">AppliedKinesiology</a>
    </dd>    
  </dl>    
  </dl>
</blockquote>
<blockquote typeof="owl:Class" vocab="http://purls.site/alternativemedicine/" id="Yoga">
  <h4 property="rdfs:label">Yoga</h4>
  <dl>
    <dt>RDF ID </dt><dd property="rdf:ID">Yoga</dd>
    <dt>Sub-Class of </dt><dd property="owl:subClassOf" typeof="Healing"><a property="rdf:resource" href="#Healing">Healing</a></dd>
    <dt>Description </dt><dd property="owl:description">Yoga is a physical, mental, and spiritual practice or discipline which originated in India.</dd>
    <dt>URI </dt><dd property="rdfs:isDefinedBy">http://purls.site/alternativemedicine/#Yoga</dd>
  </dl>
</blockquote>

<hr />

<h3>Ontology Classes: </h3>
<blockquote typeof="owl:Class" vocab="http://purls.site/alternativemedicine/" id="Acupressure">
  <h4 property="rdfs:label">Acupressure</h4>
  <dl>
    <dt>RDF ID </dt><dd property="rdf:ID">Acupressure</dd>
    <dt>Sub-Class of </dt><dd property="owl:subClassOf" typeof="TraditionalChineseMedicine"><a property="rdf:resource" href="#TraditionalChineseMedicine">TraditionalChineseMedicine</a></dd>
    <dt>Description </dt><dd property="owl:description">Physical pressure applied to acupuncture points.</dd>
    <dt>URI </dt><dd property="rdfs:isDefinedBy">http://purls.site/alternativemedicine/#Acupressure</dd>
  </dl>
</blockquote>
<blockquote typeof="owl:Class" vocab="http://purls.site/alternativemedicine/" id="Acupuncture">
  <h4 property="rdfs:label">Acupuncture</h4>
  <dl>
    <dt>RDF ID </dt><dd property="rdf:ID">Acupuncture</dd>
    <dt>Sub-Class of </dt><dd property="owl:subClassOf" typeof="TraditionalChineseMedicine"><a property="rdf:resource" href="#TraditionalChineseMedicine">TraditionalChineseMedicine</a></dd>
    <dt>Description </dt><dd property="owl:description">Thin needles inserted into the body at acupuncture points.</dd>
    <dt>URI </dt><dd property="rdfs:isDefinedBy">http://purls.site/alternativemedicine/#Acupuncture</dd>
  </dl>
</blockquote>
<blockquote typeof="owl:Class" vocab="http://purls.site/alternativemedicine/" id="AffirmativePrayer">
  <h4 property="rdfs:label">Affirmative Prayer</h4>
  <dl>
    <dt>RDF ID </dt><dd property="rdf:ID">AffirmativePrayer</dd>
    <dt>Sub-Class of </dt><dd property="owl:subClassOf" typeof="amd:SpiritualHealing"><a property="rdf:resource" href="#SpiritualHealing">SpiritualHealing</a></dd>
    <dt>Description </dt><dd property="owl:description">A form of prayer or a metaphysical technique that is focused on a positive outcome.</dd>
    <dt>URI </dt><dd property="rdfs:isDefinedBy">http://purls.site/alternativemedicine/#AffirmativePrayer</dd>
  </dl>
</blockquote>
<blockquote typeof="owl:Class" vocab="http://purls.site/alternativemedicine/" id="AlexanderTechnique">
  <h4 property="rdfs:label">Alexander Technique</h4>
  <dl>
    <dt>RDF ID </dt><dd property="rdf:ID">AlexanderTechnique</dd>
    <dt>Sub-Class of </dt><dd property="owl:subClassOf" typeof="MindBodyIntervention"><a property="rdf:resource" href="#MindBodyIntervention">MindBodyIntervention</a></dd>
    <dt>Description </dt><dd property="owl:description">An educational process that develops the ability to realign posture.</dd>
    <dt>URI </dt><dd property="rdfs:isDefinedBy">http://purls.site/alternativemedicine/#AlexanderTechnique</dd>
  </dl>
</blockquote>
<blockquote typeof="owl:Class" vocab="http://purls.site/alternativemedicine/" id="AnthroposophicMedicine">
  <h4 property="rdfs:label">Anthroposophic Medicine</h4>
  <dl>
    <dt>RDF ID </dt><dd property="rdf:ID">AnthroposophicMedicine</dd>
    <dt>Sub-Class of </dt><dd property="owl:subClassOf" typeof="amd:SpiritualHealing"><a property="rdf:resource" href="#SpiritualHealing">SpiritualHealing</a></dd>
    <dt>Description </dt><dd property="owl:description">An alterntaive medicine based on occult notions which draw on Steiner's spiritual philosophy.</dd>
    <dt>URI </dt><dd property="rdfs:isDefinedBy">http://purls.site/alternativemedicine/#AnthroposophicMedicine</dd>
  </dl>
</blockquote>
<blockquote typeof="owl:Class" vocab="http://purls.site/alternativemedicine/" id="Apitherapy">
  <h4 property="rdfs:label">Apitherapy</h4>
  <dl>
    <dt>RDF ID </dt><dd property="rdf:ID">Apitherapy</dd>
    <dt>Sub-Class of </dt><dd property="owl:subClassOf" typeof="amd:WesternEuropeMedicine"><a property="rdf:resource" href="#WesternEuropeMedicine">WesternEuropeMedicine</a></dd>
    <dt>Description </dt><dd property="owl:description">A branch of alternative medicine that uses honey bee products.</dd>
    <dt>URI </dt><dd property="rdfs:isDefinedBy">http://purls.site/alternativemedicine/#Apitherapy</dd>
  </dl>
</blockquote>
<blockquote typeof="owl:Class" vocab="http://purls.site/alternativemedicine/" id="AppliedKinesiology">
  <h4 property="rdfs:label">Applied Kinesiology</h4>
  <dl>
    <dt>RDF ID </dt><dd property="rdf:ID">AppliedKinesiology</dd>
    <dt>Sub-Class of </dt><dd property="owl:subClassOf" typeof="amd:WesternEuropeMedicine"><a property="rdf:resource" href="#WesternEuropeMedicine">WesternEuropeMedicine</a></dd>
    <dt>Description </dt><dd property="owl:description">A technique claimed to be able to diagnose illness or choose treatment by testing muscles for strength and weakness.</dd>
    <dt>URI </dt><dd property="rdfs:isDefinedBy">http://purls.site/alternativemedicine/#AppliedKinesiology</dd>
  </dl>
</blockquote>    
<blockquote typeof="owl:Class" vocab="http://purls.site/alternativemedicine/" id="Reiki">
  <h4 property="rdfs:label">Reiki</h4>
  <dl>
    <dt>RDF ID </dt><dd property="rdf:ID">Reiki</dd>
    <dt>Sub-Class of </dt><dd property="owl:subClassOf" typeof="amd:EnergyHealing"><a property="rdf:resource" href="#EnergyHealing">EnergyHealing</a></dd>
    <dt>Description </dt><dd property="owl:description">Energy Healing Technique</dd>
    <dt>URI </dt><dd property="rdfs:isDefinedBy">http://purls.site/alternativemedicine/#Reiki</dd>
  </dl>
</blockquote>
</section>