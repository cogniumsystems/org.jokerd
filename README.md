Socios OpenSocial API wrappers
================================

This project implements a set of OpenSocial wrappers for existing social
networks and common data sources like RSS/Atom feeds and e-mails. It has been developed as a part of the EU Socios project: http://www.sociosproject.eu

The main idea is to provide a common access to heterogeneous social
content sources. It translates native social network structures into
standard OpenSocial data structures.

This project consists of the main following components :

- a base implementation of all the standard OpenSocial v2 structures
- an API for accessing these structures in read/write mode
- a set of data mappers translating native social networks into standard
OpenSocial structures
- a set of social network adaptors for retrieving social content in
stream mode
- a set of generic utility libraries : a scheduler for fetching data
periodically, a set of cursors for manipulating, grouping or odering
flexibly data by various criteria (type, time, author, etc.)

The code is available under the Apache License: http://www.apache.org/licenses/LICENSE-2.0.html.
