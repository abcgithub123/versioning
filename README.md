<?xml version="1.0" encoding="UTF-8"?><xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0"><xsl:output method="html" /><xsl:include href="html_layout_msib.xsl" /><xsl:include href="html_footer_msib.xsl" /><xsl:variable name="content-year">2016</xsl:variable>
<xsl:variable name="salutation"><xsl:value-of select="//ExternalXML/salutation"/></xsl:variable><xsl:variable name="postcode"><xsl:value-of select="//ExternalXML/postcode"/></xsl:variable><xsl:variable name="THRESHOLD"><xsl:value-of select="//ExternalXML/THRESHOLD"/></xsl:variable><xsl:variable name="CREDIT_LIMIT"><xsl:value-of select="//ExternalXML/CREDIT_LIMIT"/></xsl:variable><xsl:variable name="last_x_digits"><xsl:value-of select="//ExternalXML/last_x_digits"/></xsl:variable>

<xsl:template match="kanaRoot">        <xsl:call-template name="CMALayout" /></xsl:template>

<xsl:template name="MainContent">
   <xsl:choose>   <xsl:when test="($salutation = '') or not($salutation)">Dear Customer</xsl:when>   <xsl:otherwise><xsl:value-of select="$salutation" /></xsl:otherwise>   </xsl:choose>   <p><strong>Credit Card number ending <xsl:value-of select="$last_x_digits" /></strong></p>       <p>We’re letting you know that you’ve used over  <xsl:value-of select="$THRESHOLD" /> of your credit limit on your Credit Card ending <xsl:value-of select="$last_x_digits" />. If you go over your credit limit of <xsl:value-of select="$CREDIT_LIMIT" />then a fee may be charged. You can find full information on the fees you may be charged and how to make payments, on the back of your monthly Credit Card statement.</p>       <p>If you have any questions, please call us on 03457 707 070. Lines are open 24 hours a day, 7 days a week.</p>        
                                <p>From Your HSBC Premier Team</p>
      </xsl:template>
</xsl:stylesheet>
