---
title: Pobierz stan przyjęcia usługi MFA
description: Uzyskaj listę stanów wdrażania usługi MFA dla każdego partnera przy użyciu interfejsu API REST partnera.
ms.service: partner-dashboard
ms.subservice: partnercenter-sdk
ms.date: 05/29/2020
author: amitravat
ms.author: amrava
ms.openlocfilehash: f82d163b704323c81e2948b78eb9b9d1a14ddc52
ms.sourcegitcommit: cfedd76e573c5616cf006f826f4e27f08281f7b4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/08/2020
ms.locfileid: "97767889"
---
# <a name="get-mfa-adoption-status"></a><span data-ttu-id="7dd4c-103">Pobieranie stanu wdrażania usługi MFA</span><span class="sxs-lookup"><span data-stu-id="7dd4c-103">Get MFA adoption status</span></span>

<span data-ttu-id="7dd4c-104">Dotyczy:</span><span class="sxs-lookup"><span data-stu-id="7dd4c-104">Applies to:</span></span>

- <span data-ttu-id="7dd4c-105">Interfejs API Centrum partnerskiego</span><span class="sxs-lookup"><span data-stu-id="7dd4c-105">Partner Center API</span></span>

<span data-ttu-id="7dd4c-106">W tym artykule wyjaśniono, jak uzyskać informacje o stanie wdrożenia wieloskładnikowe (MFA) dla każdego partnera w ramach dzierżawy.</span><span class="sxs-lookup"><span data-stu-id="7dd4c-106">This article explains how to get the multi-factor authentication (MFA) adoption status for each partner within a tenant.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7dd4c-107">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="7dd4c-107">Prerequisites</span></span>

- <span data-ttu-id="7dd4c-108">Poświadczenia zgodnie z opisem w temacie [uwierzytelnianie w centrum partnerskim](partner-center-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="7dd4c-108">Credentials as described in [Partner Center authentication](partner-center-authentication.md).</span></span> <span data-ttu-id="7dd4c-109">Ten scenariusz obsługuje uwierzytelnianie przy użyciu poświadczeń aplikacji i użytkownika.</span><span class="sxs-lookup"><span data-stu-id="7dd4c-109">This scenario supports authentication with App+User credentials.</span></span>

## <a name="rest-request"></a><span data-ttu-id="7dd4c-110">Żądanie REST</span><span class="sxs-lookup"><span data-stu-id="7dd4c-110">REST request</span></span>

### <a name="request-syntax"></a><span data-ttu-id="7dd4c-111">Składnia żądania</span><span class="sxs-lookup"><span data-stu-id="7dd4c-111">Request syntax</span></span>

| <span data-ttu-id="7dd4c-112">Metoda</span><span class="sxs-lookup"><span data-stu-id="7dd4c-112">Method</span></span>  | <span data-ttu-id="7dd4c-113">Identyfikator URI żądania</span><span class="sxs-lookup"><span data-stu-id="7dd4c-113">Request URI</span></span>                                                               |
|---------|---------------------------------------------------------------------------|
| <span data-ttu-id="7dd4c-114">**Pobierz**</span><span class="sxs-lookup"><span data-stu-id="7dd4c-114">**GET**</span></span> | <span data-ttu-id="7dd4c-115">[*{baseURL}*](partner-center-rest-urls.md)/V1/applicationmfaadoptionstatus></span><span class="sxs-lookup"><span data-stu-id="7dd4c-115">[*{baseURL}*](partner-center-rest-urls.md)/v1/applicationmfaadoptionstatus></span></span> |

### <a name="request-headers"></a><span data-ttu-id="7dd4c-116">Nagłówki żądań</span><span class="sxs-lookup"><span data-stu-id="7dd4c-116">Request headers</span></span>

- <span data-ttu-id="7dd4c-117">Aby uzyskać więcej informacji, zobacz [nagłówki REST Centrum partnerskiego](headers.md) .</span><span class="sxs-lookup"><span data-stu-id="7dd4c-117">See [Partner Center REST headers](headers.md) for more information.</span></span>

### <a name="request-body"></a><span data-ttu-id="7dd4c-118">Treść żądania</span><span class="sxs-lookup"><span data-stu-id="7dd4c-118">Request body</span></span>

<span data-ttu-id="7dd4c-119">Brak.</span><span class="sxs-lookup"><span data-stu-id="7dd4c-119">None.</span></span>

### <a name="request-example"></a><span data-ttu-id="7dd4c-120">Przykład żądania</span><span class="sxs-lookup"><span data-stu-id="7dd4c-120">Request example</span></span>

```http
GET https://api.partnercenter.microsoft.com/v1/applicationmfaadoptionstatus HTTP/1.1
Authorization: Bearer <token>
Host: api.partnercenter.microsoft.com
Content-Type: application/json
```

## <a name="rest-response"></a><span data-ttu-id="7dd4c-121">Odpowiedź REST</span><span class="sxs-lookup"><span data-stu-id="7dd4c-121">REST response</span></span>

<span data-ttu-id="7dd4c-122">Jeśli to się powiedzie, ta metoda zwraca kolekcję [żądań interfejsu API podsumowywanych przez zasoby aplikacji](mfa-resources.md#api-request-summarized-by-application) w treści odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="7dd4c-122">If successful, this method returns a collection of [API request summarized by Application](mfa-resources.md#api-request-summarized-by-application) resources in the response body.</span></span>

### <a name="response-success-and-error-codes"></a><span data-ttu-id="7dd4c-123">Kody sukcesu i błędów odpowiedzi</span><span class="sxs-lookup"><span data-stu-id="7dd4c-123">Response success and error codes</span></span>

<span data-ttu-id="7dd4c-124">Każda odpowiedź zawiera kod stanu HTTP, który wskazuje powodzenie lub niepowodzenie i dodatkowe informacje debugowania.</span><span class="sxs-lookup"><span data-stu-id="7dd4c-124">Each response comes with an HTTP status code that indicates success or failure and additional debugging information.</span></span> <span data-ttu-id="7dd4c-125">Użyj narzędzia do śledzenia sieci, aby odczytać ten kod, typ błędu i dodatkowe parametry.</span><span class="sxs-lookup"><span data-stu-id="7dd4c-125">Use a network trace tool to read this code, error type, and additional parameters.</span></span> <span data-ttu-id="7dd4c-126">Aby uzyskać pełną listę, zobacz [kody błędów](error-codes.md).</span><span class="sxs-lookup"><span data-stu-id="7dd4c-126">For the full list, see [Error Codes](error-codes.md).</span></span>

### <a name="response-example"></a><span data-ttu-id="7dd4c-127">Przykład odpowiedzi</span><span class="sxs-lookup"><span data-stu-id="7dd4c-127">Response example</span></span>

``` http
HTTP/1.1 200 OK
Content-Length: 313
Content-Type: application/json
MS-CorrelationId: 4cb80cbe-566b-4d8b-8b8f-af1454b73089
MS-RequestId: 566330a7-1e4b-4848-9c23-f135c70fd810
Date: Thu, 21 May 2020 22:29:17 GMT
[
    {
        "loginDate": "2020-05-20",
        "mfaCompliantRequestCount": 7,
        "totalRequestCount": 7,
        "applicationId": "14f38d7d-c4fc-448a-b2df-0fc60e75465a",
        "applicationName": ""
    },
    {
        "loginDate": "2020-05-19",
        "mfaCompliantRequestCount": 7,
        "totalRequestCount": 14,
        "applicationId": "60a00bf2-0644-4279-83b3-87ddf96f2509",
        "applicationName": ""
    }
]
```
