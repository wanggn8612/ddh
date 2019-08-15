# Overview {#DDHApiWelcome .concept}

Alibaba Cloud Dedicated Host \(DDH\) provides you with multiple APIs. We recommend that you use APIs to manage your cloud resources or develop applications.

## Limits {#section_otf_b2h_4fb .section}

There are limits to the number and specifications of dedicated hosts you can create. For more information, see [Limits](../../../../../dita-oss-bucket/SP_68/DNDDH11820440/EN-US_TP_6622.md#). When interface descriptions, optional parameter values, and available specifications are not consistent with [Limits](../../../../../dita-oss-bucket/SP_68/DNDDH11820440/EN-US_TP_6622.md#), **Limits** are applied.

## Developer options {#section_ldy_f2h_4fb .section}

This service supports HTTP and HTTPS requests, and allows the GET and POST methods. You can call a DDH API using the following methods:

-   [SDKs](https://github.com/aliyun) of different programming languages \(Recommended\)

-   Alibaba Cloud [CLI](https://www.alibabacloud.com/help/doc-detail/29993.htm)

-   Alibaba Cloud [API Explorer](https://api.aliyun.com/)

-   API URL request

**Note:** 

To use API URL requests, you must manually complete the authentication process and encode the URL for every request. This allows you to learn the authentication process for accessing Alibaba Cloud. For more information, see [Create an AccessKey](../../../../../dita-oss-bucket/SP_27/DNgameshield1843536/EN-US_TP_13782.md#).


If you use the CLI, SDKs, or API Explorer, you can skip the manual authentication process. We recommend that you use the language-specific SDK to call an API and manage your resources.

**Note:** When you call an API in the Alibaba Cloud CLI and SDK, remove the period \(.\) from request parameters . For example, use `SystemDiskCategory` for the request parameter `SystemDisk.Category`.

## Invocation methods {#section_dbt_gfh_4fb .section}

The request URL, which consists of different parameters, has a fixed request structure. The URL contains common parameters, your signature, and API-specific parameters of an API. We provide sample URL requests for every API. These sample URLs are not encoded in order to make them easy to read. You must encode the URL before making a request. After the authentication process is complete based on your signature, the results are returned to you. The response parameters are displayed if the authentication is successful, and the error message is displayed if the authentication fails. You can troubleshoot issues according to the common error codes and API-specific error codes. For more information, see [Introduction to Alibaba Cloud API](../../../../../dita-oss-bucket/SP_282/DNICMS1858991/EN-US_TP_1107.md#).

Currently, DDH shares the endpoint with ECS. For more information, see ECS[Request structure](../../../../../dita-oss-bucket/SP_2/DNA0011860945/EN-US_TP_9847.md#).

**Note:** We recommend that you use an SDK to call an API and manage your resources, to avoid manual authentication.

