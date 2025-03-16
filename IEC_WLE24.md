
# IEC_WLE24 Dataset
IEC WLE24 categorizes wireless link quality into five classes: ”Very Bad”, ”Bad”, ”Intermediate”, ”Good”, and ”Very Good”. The IEC_WLE24 dataset comprises 62,447 raw samples, each containing 27 features.
## Raw data collection
Raw IEC_WLE2024 dataset was collected by executing command in Linux, command, collected feature and description for each feature were shown bellow :
<table><thead>
  <tr>
    <th>Command</th>
    <th>Features</th>
    <th>Description</th>
  </tr></thead>
<tbody>
  <tr>
    <td rowspan="8">iw dev wlan0 station dump</td>
    <td>rx bitrate</td>
    <td>Data received rate</td>
  </tr>
  <tr>
    <td>rx packets</td>
    <td>Number of packet received</td>
  </tr>
  <tr>
    <td>tx packets</td>
    <td>Number of packet sent</td>
  </tr>
  <tr>
    <td>tx failed</td>
    <td>Number of failed when sent</td>
  </tr>
  <tr>
    <td>inactive time</td>
    <td>Time since device last had network activity</td>
  </tr>
  <tr>
    <td>beacon interval</td>
    <td>Interval between 2 consecutive beacon frames</td>
  </tr>
  <tr>
    <td>tx bytes</td>
    <td>Number of bytes sent</td>
  </tr>
  <tr>
    <td>TDLS peer</td>
    <td>Specifies whether the client is using TDLS</td>
  </tr>
  <tr>
    <td rowspan="5">iwconfig wlan0</td>
    <td>Tx excessive retries</td>
    <td>Packets failed due to excessive retries</td>
  </tr>
  <tr>
    <td>Bit Rate</td>
    <td>Current data transfer rate</td>
  </tr>
  <tr>
    <td>Frequency</td>
    <td>Network operating frequency</td>
  </tr>
  <tr>
    <td>Link Quality</td>
    <td>Connection quality, usually in X/Y form</td>
  </tr>
  <tr>
    <td>Signal level</td>
    <td>Received signal strength</td>
  </tr>
  <tr>
    <td rowspan="3">iwlist wlan0 scan</td>
    <td>Channel</td>
    <td>Number of channels</td>
  </tr>
  <tr>
    <td>Group Cipher</td>
    <td>Group encryption algorithm</td>
  </tr>
  <tr>
    <td>Pairwise Ciphers</td>
    <td>Pairwise encryption algorithm</td>
  </tr>
  <tr>
    <td rowspan="4">nmcli-f GENERAL dev show wlan0</td>
    <td>GENERAL.IP4-CONNECTIVITY</td>
    <td>IPv4 connection status</td>
  </tr>
  <tr>
    <td>GENERAL.IP6-CONNECTIVITY</td>
    <td>IPv6 connection status</td>
  </tr>
  <tr>
    <td>GENERAL.METERED</td>
    <td>Is this a data-limited connection?</td>
  </tr>
  <tr>
    <td>GENERAL.STATE</td>
    <td>Current status of network connection</td>
  </tr>
</tbody></table>

## Labeling dataset algorithm
The number of features after using Labeling dataset algorithm is 27 as shown below.
<div style="display: flex; justify-content: space-between;">

<div style="width: 30%;">
<ul>
  <li>rx bitrate</li>
  <li>rx packets</li>
  <li>tx packets</li>
  <li> tx failed </li>
  <li> inactive time </li>
  <li> beacon interval </li>
  <li> tx bytes </li>
  <li> TDLS peer_yes </li>
  <li> TDLS peer_no </li>
</ul>
</div>
<div style="width: 30%;">
<ul>
 <li> Tx excessive retries </li>
 <li> Bit Rate </li>
 <li> Frequency </li>
 <li> Channel </li>
 <li> Group Cipher_CCMP </li>
 <li> Group Cipher_TKIP </li>
 <li> Pairwise Ciphers_CCMP </li>
 <li> Pairwise Ciphers_TKIP </li>
 <li> GENERAL.IP4-CONNECTIVITY </li>
</ul>
</div>

<div style="width: 30%;">
<ul>
 <li> GENERAL.IP6-CONNECTIVITY </li>
 <li> GENERAL.METERED_no </li>
 <li> GENERAL.METERED_nunkown </li>
 <li> GENERAL.STATE_100 </li>
 <li> GENERAL.STATE_60 </li>
 <li> GENERAL.STATE_50 </li>
 <li> GENERAL.STATE_30 </li>
 <li> GENERAL.STATE_activated </li>
 <li> Label </li>
</ul>
</div>

</div>
