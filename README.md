'use client'

import { useState } from 'react'
import Image from 'next/image'
import { motion } from 'framer-motion'
import { Facebook, Mail, Github, ChevronDown, ChevronUp } from 'lucide-react'
import { Button } from "@/components/ui/button"
import { Card, CardContent } from "@/components/ui/card"

const teamMembers = [
  {
    name: "Nischal Chhukan",
    role: "Team Leader and Coder",
    bio: "Visionary leader with a passion for innovation and sustainable technology.",
    photo: "https://scontent.fktm3-1.fna.fbcdn.net/v/t39.30808-1/465576578_1911911085961013_8876150643240261015_n.jpg?stp=dst-jpg_s200x200_tt6&_nc_cat=104&ccb=1-7&_nc_sid=0ecb9b&_nc_ohc=lypbzkUepZ4Q7kNvgFd2j5-&_nc_zt=24&_nc_ht=scontent.fktm3-1.fna&_nc_gid=AKlRigFetXrOqYdFGx_h6yQ&oh=00_AYAF4vHB5PtIVsGmPiP6BZeSlLcVX3Cvw9AEPMeIsDLWEA&oe=675461E9",
    facebook: "https://www.facebook.com/nischal.chhukan.3",
    email: "alice@example.com",
    github: "https://github.com/alice"
  },
  {
    name: "Spandan Khyaju",
    role: "CTO",
    bio: "Tech genius with a knack for solving complex problems and building scalable systems.",
    photo: "/placeholder.svg?height=300&width=300",
    facebook: "https://facebook.com/bob",
    email: "bob@example.com",
    github: "https://github.com/bob"
  },
  {
    name: "Charlie Davis",
    role: "Lead Designer",
    bio: "Creative mastermind turning ideas into stunning visual experiences.",
    photo: "/placeholder.svg?height=300&width=300",
    facebook: "https://facebook.com/charlie",
    email: "charlie@example.com",
    github: "https://github.com/charlie"
  },
  {
    name: "Diana Martinez",
    role: "Marketing Director",
    bio: "Strategic thinker with a flair for creating compelling brand stories.",
    photo: "/placeholder.svg?height=300&width=300",
    facebook: "https://facebook.com/diana",
    email: "diana@example.com",
    github: "https://github.com/diana"
  },
  {
    name: "Ethan Lee",
    role: "Product Manager",
    bio: "User-centric product enthusiast with a keen eye for market trends.",
    photo: "/placeholder.svg?height=300&width=300",
    facebook: "https://facebook.com/ethan",
    email: "ethan@example.com",
    github: "https://github.com/ethan"
  }
]

export default function AboutPage() {
  const [selectedMember, setSelectedMember] = useState<number | null>(null)

  const toggleMember = (index: number) => {
    setSelectedMember(selectedMember === index ? null : index)
  }

  return (
    <div className="min-h-screen bg-[radial-gradient(ellipse_at_top_left,_var(--tw-gradient-stops))] from-blue-700 via-blue-800 to-gray-900 text-white py-20 px-4 sm:px-6 lg:px-8 relative overflow-hidden">
      <div className="absolute inset-0">
        <div className="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNTAwIiBoZWlnaHQ9IjUwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48ZmlsdGVyIGlkPSJub2lzZSI+PGZlVHVyYnVsZW5jZSB0eXBlPSJmcmFjdGFsTm9pc2UiIGJhc2VGcmVxdWVuY3k9IjAuNjUiIG51bU9jdGF2ZXM9IjMiIHN0aXRjaFRpbGVzPSJzdGl0Y2giLz48L2ZpbHRlcj48cmVjdCB3aWR0aD0iNTAwIiBoZWlnaHQ9IjUwMCIgZmlsdGVyPSJ1cmwoI25vaXNlKSIgb3BhY2l0eT0iMC41Ii8+PC9zdmc+')]"></div>
        <div className="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNTAwIiBoZWlnaHQ9IjUwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48ZmlsdGVyIGlkPSJub2lzZSI+PGZlVHVyYnVsZW5jZSB0eXBlPSJmcmFjdGFsTm9pc2UiIGJhc2VGcmVxdWVuY3k9IjAuNzUiIG51bU9jdGF2ZXM9IjQiIHN0aXRjaFRpbGVzPSJzdGl0Y2giLz48L2ZpbHRlcj48cmVjdCB3aWR0aD0iNTAwIiBoZWlnaHQ9IjUwMCIgZmlsdGVyPSJ1cmwoI25vaXNlKSIgb3BhY2l0eT0iMC43NSIvPjwvc3ZnPg==')]"></div>
      </div>
      <motion.h1 
        className="text-5xl md:text-7xl font-extrabold text-center mb-12"
        initial={{ opacity: 0, y: -50 }}
        animate={{ opacity: 1, y: 0 }}
        transition={{ duration: 0.8 }}
      >
        Meet Our Extraordinary Team
      </motion.h1>
      <motion.p 
        className="text-xl md:text-2xl text-center mb-16 max-w-3xl mx-auto"
        initial={{ opacity: 0 }}
        animate={{ opacity: 1 }}
        transition={{ delay: 0.5, duration: 0.8 }}
      >
        We're not just colleagues; we're innovators, dreamers, and game-changers. 
        Together, we're reshaping the future, one breakthrough at a time.
      </motion.p>
      <div className="max-w-7xl mx-auto">
        {teamMembers.map((member, index) => (
          <motion.div
            key={member.name}
            initial={{ opacity: 0, x: index % 2 === 0 ? -50 : 50 }}
            animate={{ opacity: 1, x: 0 }}
            transition={{ delay: index * 0.2, duration: 0.8 }}
          >
            <Card className="mb-8 overflow-hidden bg-white/5 backdrop-blur-md shadow-lg shadow-blue-500/20 hover:shadow-blue-500/40 transition-shadow duration-300">
              <CardContent className="p-0">
                <div className="flex flex-col md:flex-row">
                  <div className="md:w-1/3 relative h-64 md:h-auto">
                    <Image
                      src={member.photo}
                      alt={member.name}
                      layout="fill"
                      objectFit="cover"
                      className="transition-transform duration-300 hover:scale-110"
                    />
                  </div>
                  <div className="md:w-2/3 p-6">
                    <h2 className="text-3xl font-bold mb-2">{member.name}</h2>
                    <h3 className="text-xl text-pink-300 mb-4">{member.role}</h3>
                    <p className="mb-4">{member.bio}</p>
                    <div className="flex space-x-4 mb-4">
                      <a href={member.facebook} target="_blank" rel="noopener noreferrer">
                        <Button variant="outline" size="icon">
                          <Facebook className="h-4 w-4" />
                          <span className="sr-only">Facebook</span>
                        </Button>
                      </a>
                      <a href={`mailto:${member.email}`}>
                        <Button variant="outline" size="icon">
                          <Mail className="h-4 w-4" />
                          <span className="sr-only">Email</span>
                        </Button>
                      </a>
                      <a href={member.github} target="_blank" rel="noopener noreferrer">
                        <Button variant="outline" size="icon">
                          <Github className="h-4 w-4" />
                          <span className="sr-only">GitHub</span>
                        </Button>
                      </a>
                    </div>
                    <Button 
                      variant="ghost" 
                      onClick={() => toggleMember(index)}
                      className="w-full justify-between"
                    >
                      {selectedMember === index ? "Less Info" : "More Info"}
                      {selectedMember === index ? <ChevronUp className="ml-2 h-4 w-4" /> : <ChevronDown className="ml-2 h-4 w-4" />}
                    </Button>
                    {selectedMember === index && (
                      <motion.div
                        initial={{ opacity: 0, height: 0 }}
                        animate={{ opacity: 1, height: "auto" }}
                        exit={{ opacity: 0, height: 0 }}
                        transition={{ duration: 0.3 }}
                        className="mt-4"
                      >
                        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
                      </motion.div>
                    )}
                  </div>
                </div>
              </CardContent>
            </Card>
          </motion.div>
        ))}
      </div>
    </div>
  )
}

