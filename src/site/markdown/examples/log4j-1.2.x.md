Settings
--------------
Following settings can be used:

 * host (Mandatory): Hostname/IP-Address of the Logstasg Host
     * tcp:(the host) for TCP, e.g. tcp:127.0.0.1 or tcp:some.host.com
     * udp:(the host) for UDP, e.g. udp:127.0.0.1 or udp:some.host.com
     * (the host) for UDP, e.g. 127.0.0.1 or some.host.com
 * port (Optional): Port, default 12201
 * originHost (Optional): Originating Hostname, default FQDN Hostname
 * extractStackTrace (Optional): Post Stack-Trace to StackTrace field, default false
 * filterStackTrace (Optional): Perform Stack-Trace filtering (true/false), default false
 * mdcProfiling (Optional): Perform Profiling (Call-Duration) based on MDC Data. See MDC Profiling, default false. See [MDC Profiling](../mdcprofiling.html) for details.
 * facility (Optional): Name of the Facility, default logstash-gelf
 * threshold/level (Optional): Log-Level, default INFO
 * filter (Optional): Class-Name of a Log-Filter, default none
 * additionalFields (Optional): Post additional fields. Eg. .GelfLogHandler.additionalFields=fieldName=Value
 * mdcFields (Optional): Post additional fields, pull Values from MDC. Name of the Fields are comma-separated mdcFields=Application,Version,SomeOtherFieldName

log4j configuration
--------------

Properties:

    log4j.appender.gelf=biz.paluch.logging.gelf.log4j.GelfLogAppender
    log4j.appender.gelf.Threshold=INFO
    log4j.appender.gelf.Host=udp:localhost
    log4j.appender.gelf.Port=12201
    log4j.appender.gelf.Facility=java-test
    log4j.appender.gelf.ExtractStackTrace=true
    log4j.appender.gelf.FilterStackTrace=true
    log4j.appender.gelf.MdcProfiling=true
    log4j.appender.gelf.TimestampPattern=yyyy-MM-dd HH:mm:ss,SSSS
    log4j.appender.gelf.MaximumMessageSize=8192
    log4j.appender.gelf.AdditionalFields=fieldName1=fieldValue1,fieldName2=fieldValue2
    log4j.appender.gelf.MdcFields=mdcField1,mdcField2


XML:

    <appender name="gelf" class="biz.paluch.logging.gelf.log4j.GelfLogAppender">
        <param name="Threshold" value="INFO" />
        <param name="Host" value="udp:localhost" />
        <param name="Port" value="12201" />
        <param name="Facility" value="java-test" />
        <param name="ExtractStackTrace" value="true" />
        <param name="FilterStackTrace" value="true" />
        <param name="MdcProfiling" value="true" />
        <param name="TimestampPattern" value="yyyy-MM-dd HH:mm:ss,SSSS" />
        <param name="MaximumMessageSize" value="8192" />
        <param name="AdditionalFields" value="fieldName1=fieldValue1,fieldName2=fieldValue2" />
        <param name="MdcFields" value="mdcField1,mdcField2" />
    </appender>
    