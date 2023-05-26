// SPDX-License-identifier: GPL-3.0
pragma solidity ^0.8.0;

contract Migrantemployee
{
    struct laborersDetails
    {
    string Name;
    uint Age;
    string Gender;
    string IDProof;
    string IDProofNumber;
    uint Jobexperience;
    string JobField;
    uint MobileNo;
    string EmailID;
    }
mapping(uint=>laborersDetails) ApplicantID;
function AddNewApplicant(uint _ID,string memory _Name,uint _Age,string memory _Gender,uint _Jobexperience,string memory _JobField,string memory _IDProof,string memory _IDProofNumber,uint _MobileNo) public
   {
    ApplicantID[_ID].Name=_Name;
    ApplicantID[_ID].Age=_Age;
    ApplicantID[_ID].Gender=_Gender;
    ApplicantID[_ID].Jobexperience=_Jobexperience;
    ApplicantID[_ID].JobField=_JobField;
    ApplicantID[_ID].IDProof=_IDProof;
    ApplicantID[_ID].IDProofNumber=_IDProofNumber;
    ApplicantID[_ID].MobileNo=_MobileNo;
    }
function PersonalDetails(uint _ID) public view returns (string memory _Name,uint _Age,string memory _Gender,string memory _IDProof,string memory _IDProofNumber,uint _MobileNo){
  return (ApplicantID[_ID].Name,ApplicantID[_ID].Age,ApplicantID[_ID].Gender,ApplicantID[_ID].IDProof,ApplicantID[_ID].IDProofNumber,ApplicantID[_ID].MobileNo);
}
function WorkHistory(uint _ID) public view returns (uint _Jobexperience,string memory _JobField){
    return (ApplicantID[_ID].Jobexperience,ApplicantID[_ID].JobField);
}
}
