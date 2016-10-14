% Title = "MISP taxonomy format"
% abbrev = "MISP taxonomy format"
% category = "info"
% docName = "draft-dulaunoy-misp-taxonomy-format"
% ipr= "trust200902"
% area = "Security"
%
% date = 2016-10-13T00:00:00Z
%
% [[author]]
% initials="A."
% surname="Dulaunoy"
% fullname="Alexandre Dulaunoy"
% abbrev="CIRCL"
% organization = "Computer Incident Response Center Luxembourg"
%  [author.address]
%  email = "alexandre.dulaunoy@circl.lu"
%  phone = "+352 247 88444"
%   [author.address.postal]
%   street = "41, avenue de la gare"
%   city = "Luxembourg"
%   code = "L-1611"
%   country = "Luxembourg"
% [[author]]
% initials="A."
% surname="Iklody"
% fullname="Andras Iklody"
% abbrev="CIRCL"
% organization = "Computer Incident Response Center Luxembourg"
%  [author.address]
%  email = "andras.iklody@circl.lu"
%  phone = "+352 247 88444"
%   [author.address.postal]
%   street = "41, avenue de la gare"
%   city = "Luxembourg"
%   code = "L-1611"
%   country = "Luxembourg"

.# Abstract

This document describes the MISP taxonomy format which describes a simple JSON format to
represent machine tags (also called triple tags). A public directory of common vocabularies
MISP taxonomies is available and relies on the MISP taxonomy format.

{mainmatter}

# Introduction

Sharing threat information became a fundamental requirements in the Internet, security and intelligence community at large. Threat
information can include indicators of compromise, malicious file indicators, financial fraud indicators
or even detailed information about a threat actor. While sharing such indicators or information, classification plays an important role
to ensure adequate distribution, understanding, validation or action of the shared information. MISP taxonomies is a public repository
of known vocabularies that can be used in threat information sharing.

##  Conventions and Terminology

The key words "**MUST**", "**MUST NOT**", "**REQUIRED**", "**SHALL**", "**SHALL NOT**",
"**SHOULD**", "**SHOULD NOT**", "**RECOMMENDED**", "**MAY**", and "**OPTIONAL**" in this
document are to be interpreted as described in RFC 2119 [@!RFC2119].

# Format

## Overview

The MISP taxonomy format is in the JSON [@!RFC4627] format.

# Directory

The MISP taxonomies directory is publicly available [@?MISP-T] in a git repository. The repository
contains a directory per namespace then a file machinetag.json which contains the taxonomy as
described in the format above. In the root of the repository, a MANIFEST.json exists containing
a list of all the taxonomies.

The MANIFEST.json file is composed of an JSON object with metadata like version, license, description, url and path.
A taxonomies array describes the taxonomy available with the description, name and version field.

## Sample Manifest
~~~~
{
  "version": "20161009",
  "license": "CC-0",
  "description": "Manifest file of MISP taxonomies available.",
  "url": "https://raw.githubusercontent.com/MISP/misp-taxonomies/master/",
  "path": "machinetag.json",
  "taxonomies": [
    {
      "description": "The Admiralty Scale (also called the NATO System)
                      is used to rank the reliability of a source and
                      the credibility of an information.",
      "name": "admiralty-scale",
      "version": 1
    },
    {
      "description": "Open Source Intelligence - Classification.",
      "name": "osint",
      "version": 2
    }]
}
~~~~

# Sample

## Admiralty Scale Taxonomy

~~~~
  "namespace": "admiralty-scale",
  "description": "The Admiralty Scale (also called the NATO System)
                  is used to rank the reliability of a source and
                  the credibility of an information.",
  "version": 1,
  "predicates": [
    {
      "value": "source-reliability",
      "expanded": "Source Reliability"
    },
    {
      "value": "information-credibility",
      "expanded": "Information Credibility"
    }
  ],
  "values": [
    {
      "predicate": "source-reliability",
      "entry": [
        {
          "value": "a",
          "expanded": "Completely reliable"
        },
        {
          "value": "b",
          "expanded": "Usually reliable"
        },
        {
          "value": "c",
          "expanded": "Fairly reliable"
        },
        {
          "value": "d",
          "expanded": "Not usually reliable"
        },
        {
          "value": "e",
          "expanded": "Unreliable"
        },
        {
          "value": "f",
          "expanded": "Reliability cannot be judged"
        }
      ]
    },
    {
      "predicate": "information-credibility",
      "entry": [
        {
          "value": "1",
          "expanded": "Confirmed by other sources"
        },
        {
          "value": "2",
          "expanded": "Probably true"
        },
        {
          "value": "3",
          "expanded": "Possibly true"
        },
        {
          "value": "4",
          "expanded": "Doubtful"
        },
        {
          "value": "5",
          "expanded": "Improbable"
        },
        {
          "value": "6",
          "expanded": "Truth cannot be judged"
        }
      ]
    }
  ]
}
~~~~

## Open Source Intelligence - Classification

~~~~
{
  "values": [
    {
      "entry": [
        {
          "expanded": "Blog post",
          "value": "blog-post"
        },
        {
          "expanded": "Technical or analysis report",
          "value": "technical-report"
        },
        {
          "expanded": "News report",
          "value": "news-report"
        },
        {
          "expanded": "Pastie-like website",
          "value": "pastie-website"
        },
        {
          "expanded": "Electronic forum",
          "value": "electronic-forum"
        },
        {
          "expanded": "Mailing-list",
          "value": "mailing-list"
        },
        {
          "expanded": "Block or Filter List",
          "value": "block-or-filter-list"
        },
        {
          "expanded": "Expansion",
          "value": "expansion"
        }
      ],
      "predicate": "source-type"
    },
    {
      "predicate": "lifetime",
      "entry": [
        {
          "value": "perpetual",
          "expanded": "Perpetual",
          "description": "Information available publicly on long-term"
        },
        {
          "value": "ephemeral",
          "expanded": "Ephemeral",
          "description": "Information available publicly on short-term"
        }
      ]
    },
    {
      "predicate": "certainty",
      "entry": [
        {
          "numerical_value": 100,
          "value": "100",
          "expanded": "100% Certainty",
          "description": "100% Certainty"
        },
        {
          "numerical_value": 93,
          "value": "93",
          "expanded": "93% Almost certain",
          "description": "93% Almost certain"
        },
        {
          "numerical_value": 75,
          "value": "75",
          "expanded": "75% Probable",
          "description": "75% Probable"
        },
        {
          "numerical_value": 50,
          "value": "50",
          "expanded": "50% Chances about even",
          "description": "50% Chances about even"
        },
        {
          "numerical_value": 30,
          "value": "30",
          "expanded": "30% Probably not",
          "description": "30% Probably not"
        },
        {
          "numerical_value": 7,
          "value": "7",
          "expanded": "7% Almost certainly not",
          "description": "7% Almost certainly not"
        },
        {
          "numerical_value": 0,
          "value": "0",
          "expanded": "0% Impossibility",
          "description": "0% Impossibility"
        }
      ]
    }
  ],
  "namespace": "osint",
  "description": "Open Source Intelligence - Classification",
  "version": 3,
  "predicates": [
    {
      "value": "source-type",
      "expanded": "Source Type"
    },
    {
      "value": "lifetime",
      "expanded": "Lifetime of the information
                   as Open Source Intelligence"
    },
    {
      "value": "certainty",
      "expanded": "Certainty of the elements mentioned
                   in this Open Source Intelligence"
    }
  ]
}

~~~~

# Acknowledgements

The authors wish to thank all the MISP community to support the creation
of open standards in threat intelligence sharing.

<reference anchor='MISP-P' target='https://github.com/MISP'>
  <front>
   <title>MISP Project - Malware Information Sharing Platform and Threat Sharing</title>
   <author initials='' surname='MISP' fullname='MISP Community'></author>
   <date></date>
  </front>
</reference>

<reference anchor='MISP-T' target='https://github.com/MISP/misp-taxonomies'>
  <front>
   <title>MISP Taxonomies - shared and common vocabularies of tags</title>
   <author initials='' surname='MISP' fullname='MISP Community'></author>
   <date></date>
  </front>
</reference>


{backmatter}

