Overview
=========

This project implements a set of OpenSocial wrappers for existing social
networks (so far only Twitter and Facebook, Google+ is in progress) and common data sources like 
RSS/Atom feeds and e-mails. It has been developed as a part of the EU Socios project: http://www.sociosproject.eu

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

Package Description
=====================
* org.jokerd - the root project containing Maven configurations used
to download and build all other projects
* org.jokerd.opensocial.api - main OpenSocial datastructures + basic
infrastructure used to implement OpenSocial API calls; does not
contain real call handlers (they are not implemented)
* org.jokerd.opensocial.api/src/main/java/org/jokerd/opensocial/api/events -contains implementation of some OpenSocial API calls allowing to retrieve the information about ActivityStreams, People, and Activities. It provides an infrastructure to implement any OpenSocial event-based asynchroneous calls (based on the EventBus pattern).
* org.jokerd.opensocial.base - Basic utilities used by other repositories
* org.jokerd.opensocial.oauth - an utility project used by
Twitter/Facebook adaptors; contains OAuth connectors
* org.jokerd.sandbox.tests - Contains some examples; a demo of getting
info from Twitter and RSS feeds
* org.jokerd.opensocial.store - A simple local cache for downloaded
JSON structures, such as activities. The implementation is based on an
object-oriented database OrientDB (http://www.orientdb.org).
* org.jokerd.opensocial.twitter - a Twitter adapter representing twit
stream as an ActivityStream
* org.jokerd.opensocial.facebook - a Facebook adapter providing access
to Facebook activities (ActivityStream)
* org.jokerd.opensocial.feeds - an adapter for RSS/Atom feeds
transforming feeds in ActivityStream items

Data structures
==============
"org.jokerd.opensocial.api / src / main / java / org / jokerd /
opensocial / api / model /"  package implements the following
data structures of the OpenSocial v2.0.1 Specification:
* Account - http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Social-Data.xml#Account
* ActionLink - http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Social-Data.xml#ActionLink
* Activity - http://opensocial-resources.googlecode.com/svn/spec/1.0/Social-Data.xml#Activity
(deprecated in v2.0)
* ActivityEntry -
http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Social-Data.xml#ActivityEntry
* ActivityObject -
http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Social-Data.xml#ActivityObject
* Address - http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Social-Data.xml#Address
* Album - http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Social-Data.xml#Album
* AppData - http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Social-Data.xml#AppData
* Group - http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Social-Data.xml#Group
* MediaItem - http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Social-Data.xml#MediaItem
* MediaLink - http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Social-Data.xml#MediaLink
* Message - http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Social-Data.xml#Message
* Organization  -
http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Social-Data.xml#Organization
* Person - http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Social-Data.xml#Person
* PersonMin  - http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Social-Data.xml#Person
(minimal set of properties)

Basic data structures and utility classes:
* Collection - http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Core-Data.xml#Collection
* DomainName - http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Core-Data.xml#Domain-Name
* Name -  http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Core-Data.xml#Name
* ObjectId -  http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Core-Data.xml#Object-Id
* UserId - http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Core-Data.xml#User-Id
* GroupId - http://opensocial-resources.googlecode.com/svn/spec/2.0.1/Social-Data.xml#Group-ID
* LocalIdEncoder
* DateUTCOffset
