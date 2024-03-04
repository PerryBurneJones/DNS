# Complex network traffic analysis code

class NetworkTrafficAnalyzer:
    def __init__(self):
        self.traffic_data = []

    def add_packet(self, packet):
        self.traffic_data.append(packet)

    def analyze_traffic(self):
        total_packets = len(self.traffic_data)
        total_bytes = sum(packet.size for packet in self.traffic_data)
        average_size = total_bytes / total_packets if total_packets > 0 else 0

        print("Total packets:", total_packets)
        print("Total bytes:", total_bytes)
        print("Average packet size:", average_size)


class Packet:
    def __init__(self, size):
        self.size = size


# Usage
analyzer = NetworkTrafficAnalyzer()
analyzer.add_packet(Packet(150))
analyzer.add_packet(Packet(300))
analyzer.add_packet(Packet(200))
analyzer.analyze_traffic()
