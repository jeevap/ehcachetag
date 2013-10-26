# EHCache Taglib
## Introduction

## Basic example

ehcache.xml

	<cache name="ehcachetagCache" eternal="false"
		maxElementsInMemory="10000" overflowToDisk="false" diskPersistent="false"
		timeToIdleSeconds="0" timeToLiveSeconds="10"
		memoryStoreEvictionPolicy="LRU" statistics="true" />

web.xml:

	<context-param>
        <param-name>ehcachetag.cacheKeyMetaFactoryClass</param-name>
        <param-value>nl.siegmann.ehcachetag.DefaultCacheKeyMetaFactory</param-value>
    </context-param>


test.jsp:

	<%@ taglib prefix="ect" uri="http://www.siegmann.nl/ehcachetag/taglib" %>
	<ect:cache key="test">
    	<h2>Content generated on <%= new java.util.Date() %> (<%= 		System.currentTimeMillis() %>)</h2>
	</ect:cache>

