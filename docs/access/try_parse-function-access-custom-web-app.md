---
title: Try_Parse 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ed35263c-b0ad-4269-9caa-c0164015e980
description: 将文本值分析为应用程序的区域性中的指定数据类型, 如果转换无效, 则返回 Null。
ms.openlocfilehash: 5d201557607d2d18c36238d9658b705a6a49fda8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427526"
---
# <a name="tryparse-function-access-custom-web-app"></a><span data-ttu-id="f931f-103">Try_Parse 函数 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="f931f-103">Try_Parse Function (Access custom web app)</span></span>

<span data-ttu-id="f931f-104">将文本值分析为应用程序的区域性中的指定数据类型, 如果转换无效, 则返回 Null。</span><span class="sxs-lookup"><span data-stu-id="f931f-104">Parses a text value to the specified data type in the culture of the application or returns Null if the conversion is not valid.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f931f-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="f931f-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="f931f-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="f931f-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="f931f-107">语法</span><span class="sxs-lookup"><span data-stu-id="f931f-107">Syntax</span></span>

 <span data-ttu-id="f931f-108">**Try_Parse**(*TextExpression*, *DataType*)</span><span class="sxs-lookup"><span data-stu-id="f931f-108">**Try_Parse** (*TextExpression*, *DataType*)</span></span> 
  
<span data-ttu-id="f931f-109">**Try_Parse**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="f931f-109">The **Try_Parse** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="f931f-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="f931f-110">**Argument name**</span></span>|<span data-ttu-id="f931f-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="f931f-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="f931f-112">*TextExpression*</span><span class="sxs-lookup"><span data-stu-id="f931f-112">*TextExpression*</span></span>  <br/> |<span data-ttu-id="f931f-113">表示要分析为指定数据类型的格式化值的文本表达式。</span><span class="sxs-lookup"><span data-stu-id="f931f-113">A text expression representing the formatted value to parse into the specified data type.</span></span>  <br/> |
| <span data-ttu-id="f931f-114">*DataType*</span><span class="sxs-lookup"><span data-stu-id="f931f-114">*DataType*</span></span>  <br/> |<span data-ttu-id="f931f-115">要在其中分析*TextExpression*的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f931f-115">The data type into which to parse  *TextExpression*  .</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f931f-116">说明</span><span class="sxs-lookup"><span data-stu-id="f931f-116">Remarks</span></span>

<span data-ttu-id="f931f-117">仅使用**Try_Parse**将字符串转换为日期/时间和数字类型。</span><span class="sxs-lookup"><span data-stu-id="f931f-117">Use **Try_Parse** only for converting from string to date/time and number types.</span></span> <span data-ttu-id="f931f-118">对于常规类型转换, 请继续使用**Convert**。</span><span class="sxs-lookup"><span data-stu-id="f931f-118">For general type conversions, continue to use **Convert**.</span></span> 
  

