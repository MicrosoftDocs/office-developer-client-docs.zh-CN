---
title: Stat 方法-ActiveX 数据对象 (ADO)
TOCTitle: Stat method (ADO)
ms:assetid: d3d3976b-14d4-dee0-412d-a37bc72fbfd3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250056(v=office.15)
ms:contentKeyID: 48547916
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3853c42fab9de9e06691ae0e8efe20e23c410121
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949290"
---
# <a name="stat-method-ado"></a><span data-ttu-id="3c60c-102">Stat 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="3c60c-102">Stat method (ADO)</span></span>

<span data-ttu-id="3c60c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="3c60c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3c60c-104">可检索有关 **Stream** 对象的信息。</span><span class="sxs-lookup"><span data-stu-id="3c60c-104">Retrieves information about a **Stream** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="3c60c-105">语法</span><span class="sxs-lookup"><span data-stu-id="3c60c-105">Syntax</span></span>

<span data-ttu-id="3c60c-106">长*流*。Stat （*StatStg*、 *StatFlag*）</span><span class="sxs-lookup"><span data-stu-id="3c60c-106">Long *stream*.Stat(*StatStg*, *StatFlag*)</span></span>

## <a name="return-value"></a><span data-ttu-id="3c60c-107">返回值</span><span class="sxs-lookup"><span data-stu-id="3c60c-107">Return value</span></span>

<span data-ttu-id="3c60c-108">长整型值，指示操作的状态。</span><span class="sxs-lookup"><span data-stu-id="3c60c-108">A long value indicating the status of the operation.</span></span>

## <a name="parameters"></a><span data-ttu-id="3c60c-109">参数</span><span class="sxs-lookup"><span data-stu-id="3c60c-109">Parameters</span></span>

|<span data-ttu-id="3c60c-110">参数</span><span class="sxs-lookup"><span data-stu-id="3c60c-110">Parameter</span></span>|<span data-ttu-id="3c60c-111">说明</span><span class="sxs-lookup"><span data-stu-id="3c60c-111">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="3c60c-112">*StatStg*</span><span class="sxs-lookup"><span data-stu-id="3c60c-112">*StatStg*</span></span> |<span data-ttu-id="3c60c-p101">STATSTG 结构，将使用流信息进行填充。ADO Stream 对象所用的 Stat 方法的实现不会填充该结构的所有字段。</span><span class="sxs-lookup"><span data-stu-id="3c60c-p101">A STATSTG structure that will be filled in with information about the stream. The implementation of the Stat method used by the ADO Stream object does not fill in all of the fields of the structure.</span></span>|
|<span data-ttu-id="3c60c-115">*StatFlag*</span><span class="sxs-lookup"><span data-stu-id="3c60c-115">*StatFlag*</span></span> |<span data-ttu-id="3c60c-p102">可指定此方法不在 STATSTG 结构中返回某些成员，从而省去了内存分配操作。值从 STATFLAG 枚举中提取。</span><span class="sxs-lookup"><span data-stu-id="3c60c-p102">Specifies that this method does not return some of the members in the STATSTG structure, thus saving a memory allocation operation. Values are taken from the STATFLAG enumeration.</span></span><br/><br/><span data-ttu-id="3c60c-118">STATFLAG 枚举具有两个值：</span><span class="sxs-lookup"><span data-stu-id="3c60c-118">The STATFLAG enumeration has two values:</span></span><br/><span data-ttu-id="3c60c-119">-STATFLAG_DEFAULT: 0</span><span class="sxs-lookup"><span data-stu-id="3c60c-119">- STATFLAG_DEFAULT: 0</span></span><br/><span data-ttu-id="3c60c-120">-STATFLAG_NONAME: 1</span><span class="sxs-lookup"><span data-stu-id="3c60c-120">- STATFLAG_NONAME: 1</span></span> |


## <a name="remarks"></a><span data-ttu-id="3c60c-121">备注</span><span class="sxs-lookup"><span data-stu-id="3c60c-121">Remarks</span></span>

<span data-ttu-id="3c60c-122">为 ADO Stream 对象实现的 Stat 方法会填充 STATSTG 结构的以下字段：</span><span class="sxs-lookup"><span data-stu-id="3c60c-122">The version of the Stat method implemented for the ADO Stream object fills in the following fields of the STATSTG structure:</span></span>

|<span data-ttu-id="3c60c-123">字段</span><span class="sxs-lookup"><span data-stu-id="3c60c-123">Field</span></span>|<span data-ttu-id="3c60c-124">说明</span><span class="sxs-lookup"><span data-stu-id="3c60c-124">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="3c60c-125">*pwcsName*</span><span class="sxs-lookup"><span data-stu-id="3c60c-125">*pwcsName*</span></span> |<span data-ttu-id="3c60c-126">如果有包含流中的名称的字符串和 StatFlag 值 STATFLAG\_无名未指定。</span><span class="sxs-lookup"><span data-stu-id="3c60c-126">A string containing the name of the stream, if one is available and the StatFlag value STATFLAG\_NONAME was not specified.</span></span>|
|<span data-ttu-id="3c60c-127">*cbSize*</span><span class="sxs-lookup"><span data-stu-id="3c60c-127">*cbSize*</span></span> |<span data-ttu-id="3c60c-128">指定流或字节数组的大小，以字节计。</span><span class="sxs-lookup"><span data-stu-id="3c60c-128">Specifies the size in bytes of the stream or byte array.</span></span>|
|<span data-ttu-id="3c60c-129">*mtime*</span><span class="sxs-lookup"><span data-stu-id="3c60c-129">*mtime*</span></span> |<span data-ttu-id="3c60c-130">指示此存储、流或字节数组的上次修改时间。</span><span class="sxs-lookup"><span data-stu-id="3c60c-130">Indicates the last modification time for this storage, stream, or byte array.</span></span>|
|<span data-ttu-id="3c60c-131">*ctime*</span><span class="sxs-lookup"><span data-stu-id="3c60c-131">*ctime*</span></span> |<span data-ttu-id="3c60c-132">指示此存储、流或字节数组的创建时间。</span><span class="sxs-lookup"><span data-stu-id="3c60c-132">Indicates the creation time for this storage, stream, or byte array.</span></span>|
|<span data-ttu-id="3c60c-133">*atime*</span><span class="sxs-lookup"><span data-stu-id="3c60c-133">*atime*</span></span> |<span data-ttu-id="3c60c-134">指示此存储、流或字节数组的上次访问时间。</span><span class="sxs-lookup"><span data-stu-id="3c60c-134">Indicates the last access time for this storage, stream or byte array.</span></span>|

<span data-ttu-id="3c60c-135">如果 STATFLAG\_在 StatFlag 参数中指定无名，则不返回流的名称。</span><span class="sxs-lookup"><span data-stu-id="3c60c-135">If STATFLAG\_NONAME is specified in the StatFlag parameter, the name of the stream is not returned.</span></span>

<span data-ttu-id="3c60c-136">如果 STATFLAG\_无名未在 StatFlag 参数中指定和没有可用于当前流的名称，此值将 E\_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="3c60c-136">If STATFLAG\_NONAME was not specified in the StatFlag parameter, and there is no name available for the current stream, this value will be E\_NOTIMPL.</span></span>

