<?xml version="1.0" encoding="UTF-8"?>
<wsdl:definitions name="ArgobasicService" targetNamespace="http://www.navis.com/services/argobasicservice" xmlns:soap="http://schemas.xmlsoap.org/wsdl/soap/" xmlns:tns="http://www.navis.com/services/argobasicservice" xmlns:wsdl="http://schemas.xmlsoap.org/wsdl/">

     <wsdl:documentation xmlns:wsdl="http://schemas.xmlsoap.org/wsdl/">
Argo Services </wsdl:documentation>


     <wsdl:types>

          <xsd:schema elementFormDefault="qualified" targetNamespace="http://www.navis.com/services/argobasicservice" xmlns:xsd="http://www.w3.org/2001/XMLSchema">


               <xsd:element name="basicInvoke">

                    <xsd:complexType>

                         <xsd:sequence>

                              <xsd:element name="scopeCoordinateIds" type="xsd:string"/>

                              <xsd:element maxOccurs="1" minOccurs="1" name="xmlDoc" type="xsd:string"/>

                         </xsd:sequence>

                    </xsd:complexType>

               </xsd:element>


               <xsd:element name="basicInvokeResponse">

                    <xsd:complexType>

                         <xsd:sequence>

                              <xsd:element name="basicInvokeResponse" type="xsd:string"/>

                         </xsd:sequence>

                    </xsd:complexType>

               </xsd:element>


               <xsd:element name="invokeRequest">

                    <xsd:complexType>

                         <xsd:sequence>

                              <xsd:element name="scopeCoordinateIds" type="xsd:string"/>

                              <xsd:element maxOccurs="1" minOccurs="1" name="request" type="xsd:string"/>

                              <xsd:element maxOccurs="1" minOccurs="1" name="handler" type="xsd:string"/>

                              <xsd:element maxOccurs="1" minOccurs="1" name="locale" type="xsd:string"/>

                         </xsd:sequence>

                    </xsd:complexType>

               </xsd:element>


               <xsd:element name="invokeRequestResponse">

                    <xsd:complexType>

                         <xsd:sequence>

                              <xsd:element name="basicInvokeResponse" type="xsd:string"/>

                         </xsd:sequence>

                    </xsd:complexType>

               </xsd:element>


          </xsd:schema>

     </wsdl:types>


     <wsdl:message name="basicInvokeRequest">

          <wsdl:part element="tns:basicInvoke" name="basicInvoke"/>

     </wsdl:message>


     <wsdl:message name="basicInvokeResponse">

          <wsdl:part element="tns:basicInvokeResponse" name="basicInvokeResponse"/>

     </wsdl:message>


     <wsdl:message name="invokeRequest">

          <wsdl:part element="tns:invokeRequest" name="invokeRequest"/>

     </wsdl:message>


     <wsdl:message name="invokeRequestResponse">

          <wsdl:part element="tns:basicInvokeResponse" name="basicInvokeResponse"/>

     </wsdl:message>


     <wsdl:portType name="ArgobasicServicePort">


        <!-- name of your wrapped method -->

          <wsdl:operation name="basicInvoke">

               <wsdl:input message="tns:basicInvokeRequest"/>

               <wsdl:output message="tns:basicInvokeResponse"/>

          </wsdl:operation>


          <wsdl:operation name="invoke">

               <wsdl:input message="tns:invokeRequest"/>

               <wsdl:output message="tns:basicInvokeResponse"/>

          </wsdl:operation>


     </wsdl:portType>


     <wsdl:binding name="ArgobasicServiceSoapBinding" type="tns:ArgobasicServicePort">

          <soap:binding style="document" transport="http://schemas.xmlsoap.org/soap/http"/>

        <!-- name of your wrapped method -->

          <wsdl:operation name="basicInvoke">

               <soap:operation soapAction=""/>

               <wsdl:input>

                    <soap:body use="literal"/>

               </wsdl:input>

               <wsdl:output>

                    <soap:body use="literal"/>

               </wsdl:output>

          </wsdl:operation>


          <wsdl:operation name="invoke">

               <soap:operation soapAction=""/>

               <wsdl:input>

                    <soap:body use="literal"/>

               </wsdl:input>

               <wsdl:output>

                    <soap:body use="literal"/>

               </wsdl:output>

          </wsdl:operation>


     </wsdl:binding>


     <wsdl:service name="ArgobasicService">

          <wsdl:port binding="tns:ArgobasicServiceSoapBinding" name="ArgobasicServicePort">

               <soap:address location="http://logintvvnt01:9080/apex/services/argobasicservice"/>

          </wsdl:port>

     </wsdl:service>


</wsdl:definitions>
