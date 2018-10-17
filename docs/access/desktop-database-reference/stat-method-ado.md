---
title: Stat 方法-ActiveX 数据对象 (ADO)
TOCTitle: Stat Method (ADO)
ms:assetid: d3d3976b-14d4-dee0-412d-a37bc72fbfd3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250056(v=office.15)
ms:contentKeyID: 48547916
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5d2b8c69df8caba93f693194573d057d52dffeb8
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465987"
---
# <a name="stat-method-ado"></a><span data-ttu-id="4e27f-102">Stat 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="4e27f-102">Stat Method (ADO)</span></span>


<span data-ttu-id="4e27f-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="4e27f-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="4e27f-104">可检索有关 **Stream** 对象的信息。</span><span class="sxs-lookup"><span data-stu-id="4e27f-104">Retrieves information about a **Stream** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="4e27f-105">语法</span><span class="sxs-lookup"><span data-stu-id="4e27f-105">Syntax</span></span>

<span data-ttu-id="4e27f-106">长*流*。Stat （*StatStg*、 *StatFlag*）</span><span class="sxs-lookup"><span data-stu-id="4e27f-106">Long *stream*.Stat(*StatStg*, *StatFlag*)</span></span>

## <a name="return-value"></a><span data-ttu-id="4e27f-107">返回值</span><span class="sxs-lookup"><span data-stu-id="4e27f-107">Return Value</span></span>

<span data-ttu-id="4e27f-108">长整型值，指示操作的状态。</span><span class="sxs-lookup"><span data-stu-id="4e27f-108">A long value indicating the status of the operation.</span></span>

## <a name="parameters"></a><span data-ttu-id="4e27f-109">参数</span><span class="sxs-lookup"><span data-stu-id="4e27f-109">Parameters</span></span>

  - <span data-ttu-id="4e27f-110">*StatStg*</span><span class="sxs-lookup"><span data-stu-id="4e27f-110">*StatStg*</span></span>

  - <span data-ttu-id="4e27f-p101">STATSTG 结构，将使用流信息进行填充。ADO Stream 对象所用的 Stat 方法的实现不会填充该结构的所有字段。</span><span class="sxs-lookup"><span data-stu-id="4e27f-p101">A STATSTG structure that will be filled in with information about the stream. The implementation of the Stat method used by the ADO Stream object does not fill in all of the fields of the structure.</span></span>

  - <span data-ttu-id="4e27f-113">*StatFlag*</span><span class="sxs-lookup"><span data-stu-id="4e27f-113">*StatFlag*</span></span>

  - <span data-ttu-id="4e27f-p102">可指定此方法不在 STATSTG 结构中返回某些成员，从而省去了内存分配操作。值从 STATFLAG 枚举中提取。</span><span class="sxs-lookup"><span data-stu-id="4e27f-p102">Specifies that this method does not return some of the members in the STATSTG structure, thus saving a memory allocation operation. Values are taken from the STATFLAG enumeration.</span></span>  
      
    <span data-ttu-id="4e27f-116">STATFLAG 枚举包括两个值：</span><span class="sxs-lookup"><span data-stu-id="4e27f-116">The STATFLAG enumeration has two values</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p><span data-ttu-id="4e27f-117">常量</span><span class="sxs-lookup"><span data-stu-id="4e27f-117">Constant</span></span></p></th>
    <th><p><span data-ttu-id="4e27f-118">值</span><span class="sxs-lookup"><span data-stu-id="4e27f-118">Value</span></span></p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="4e27f-119">STATFLAG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="4e27f-119">STATFLAG_DEFAULT</span></span></p></td>
    <td><p><span data-ttu-id="4e27f-120">0</span><span class="sxs-lookup"><span data-stu-id="4e27f-120">0</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="4e27f-121">STATFLAG_NONAME</span><span class="sxs-lookup"><span data-stu-id="4e27f-121">STATFLAG_NONAME</span></span></p></td>
    <td><p><span data-ttu-id="4e27f-122">1</span><span class="sxs-lookup"><span data-stu-id="4e27f-122">1</span></span></p></td>
    </tr>
    </tbody>
    </table>


## <a name="remarks"></a><span data-ttu-id="4e27f-123">备注</span><span class="sxs-lookup"><span data-stu-id="4e27f-123">Remarks</span></span>

<span data-ttu-id="4e27f-124">为 ADO Stream 对象实现的 Stat 方法会填充 STATSTG 结构的以下字段：</span><span class="sxs-lookup"><span data-stu-id="4e27f-124">The version of the Stat method implemented for the ADO Stream object fills in the following fields of the STATSTG structure:</span></span>

  - <span data-ttu-id="4e27f-125">*pwcsName*</span><span class="sxs-lookup"><span data-stu-id="4e27f-125">*pwcsName*</span></span>

  - <span data-ttu-id="4e27f-126">如果有包含流中的名称的字符串和 StatFlag 值 STATFLAG\_无名未指定。</span><span class="sxs-lookup"><span data-stu-id="4e27f-126">A string containing the name of the stream, if one is available and the StatFlag value STATFLAG\_NONAME was not specified.</span></span>

  - <span data-ttu-id="4e27f-127">*cbSize*</span><span class="sxs-lookup"><span data-stu-id="4e27f-127">*cbSize*</span></span>

  - <span data-ttu-id="4e27f-128">指定流或字节数组的大小，以字节计。</span><span class="sxs-lookup"><span data-stu-id="4e27f-128">Specifies the size in bytes of the stream or byte array.</span></span>

  - <span data-ttu-id="4e27f-129">*mtime*</span><span class="sxs-lookup"><span data-stu-id="4e27f-129">*mtime*</span></span>

  - <span data-ttu-id="4e27f-130">指示此存储、流或字节数组的上次修改时间。</span><span class="sxs-lookup"><span data-stu-id="4e27f-130">Indicates the last modification time for this storage, stream, or byte array.</span></span>

  - <span data-ttu-id="4e27f-131">*ctime*</span><span class="sxs-lookup"><span data-stu-id="4e27f-131">*ctime*</span></span>

  - <span data-ttu-id="4e27f-132">指示此存储、流或字节数组的创建时间。</span><span class="sxs-lookup"><span data-stu-id="4e27f-132">Indicates the creation time for this storage, stream, or byte array.</span></span>

  - <span data-ttu-id="4e27f-133">*atime*</span><span class="sxs-lookup"><span data-stu-id="4e27f-133">*atime*</span></span>

  - <span data-ttu-id="4e27f-134">指示此存储、流或字节数组的上次访问时间。</span><span class="sxs-lookup"><span data-stu-id="4e27f-134">Indicates the last access time for this storage, stream or byte array.</span></span>

<span data-ttu-id="4e27f-135">如果 STATFLAG\_在 StatFlag 参数中指定无名，则不返回流的名称。</span><span class="sxs-lookup"><span data-stu-id="4e27f-135">If STATFLAG\_NONAME is specified in the StatFlag parameter, the name of the stream is not returned.</span></span>

<span data-ttu-id="4e27f-136">如果 STATFLAG\_无名未在 StatFlag 参数中指定和没有可用于当前流的名称，此值将 E\_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="4e27f-136">If STATFLAG\_NONAME was not specified in the StatFlag parameter, and there is no name available for the current stream, this value will be E\_NOTIMPL.</span></span>
